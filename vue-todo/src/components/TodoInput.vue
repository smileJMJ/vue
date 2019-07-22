<template>
  <div>
      <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter = "addTodo" placeholder="Type what you have to do">
        <button v-on:click="addTodo">추가</button>
      </div>
  </div>
</template>

<script>
    export default {
        data() {
          return {
            newTodoItem: ''
          }
        },
      methods: {
          addTodo() {
            if(!this.newTodoItem) {
              var value = this.newTodoItem && this.newTodoItem.trim();
              localStorage.setItem(value, value);
              this.clearInput();
            }
          },
        clearInput() {
            this.newTodoItem = '';
        }
      }
    }
</script>

<style scoped>

</style>
