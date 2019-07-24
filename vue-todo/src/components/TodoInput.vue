<template>
  <div class="inputBox shadow">
      <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" placeholder="Type what you have to do">
    <button v-on:click="addTodo" class="addContainer">
        <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </button>
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
                  if(this.newTodoItem !== '') {
                      var value  = this.newTodoItem && this.newTodoItem.trim();
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
    .inputBox {overflow:hidden; background:#fff; border-radius:5px;}
    .inputBox input {box-sizing:border-box; width:calc(100% - 3rem); height:50px; padding:0 20px;  font-size:0.9rem; line-height:50px;border-style:none;}
    .addContainer {display:block; float:right; width:3rem; height:50px; padding:0; background:linear-gradient(to right, #6478FB, #8763FB) ; border:0; border-radius:0 5px 5px 0; cursor:pointer;}
    .addBtn {color:#fff; vertical-align:middle;}
</style>
