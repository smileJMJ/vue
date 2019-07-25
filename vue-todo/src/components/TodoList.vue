<template>
  <section>
      <ul>
          <li v-for="(todoItem, index) in propsdata" :key="todoItem" class="shadow">
            <i class="checkBtn fas fa-check" aria-hidden="true"></i>
            {{ todoItem }}
            <button class="removeBtn"@click="removeTodo(todoItem, index)">
              <i class="far fa-trash-alt" aria-hidden="true"></i>
            </button>
          </li>
      </ul>
  </section>
</template>

<script>
    export default {
        props: ['propsdata'],
      methods: {
          removeTodo(todoItem, index) {
           this.$emit('removeTodo', todoItem, index);
          }
      }
    }
</script>

<style scoped>
  ul {list-style:none; padding-left:0; margin-top:0; text-align:left;}
  li {display:flex; min-height:50px; height:50px; line-height:50px; margin:0.5rem 0; padding:0 0.9rem; background:#fff; border-radius:5px;}
  .checkBtn {padding:0; margin-right:5px; color:#62acde; line-height:45px; background:transparent; border:0; cursor:pointer;}
  .removeBtn {padding:0; margin-left:auto; color:#de434343; background:transparent; border:0; cursor:pointer;}
</style>
