<template>
  <div id="app">
    <Todo-Header></Todo-Header>
    <Todo-Input v-on:addTodoItem="addOneItem"></Todo-Input>
    <Todo-List v-bind:propsdata="todoItems" v-on:removeItem="removeOneItem"></Todo-List>
    <Todo-Footer></Todo-Footer>
  </div>
</template>

<script>

import TodoHeader from './components/TodoHeader.vue'
import TodoInput from "./components/TodoInput.vue"
import TodoList from "./components/TodoList.vue"
import TodoFooter from "./components/TodoFooter.vue"

export default {
  data: function() {
    return {
      todoItems : []
    }
  },
  methods: {
    addOneItem : function(todoItem) {
      var obj = {completed:false , item:todoItem}
      localStorage.setItem(todoItem,JSON.stringify(obj));
      this.todoItems.push(obj);
    },
    removeOneItem: function(todoItem,index) {
      localStorage.removeItem(todoItem.item); // todoItemはobjectなのでキーであるitemまで指定しないとlocalstorageで削除されない
      this.todoItems.splice(index,1);
    }
  },
  created:function(){
    if(localStorage.length>0){
      for(var i = 0;i<localStorage.length;i++) {
        if((localStorage.key(i) !=="loglevel:webpack-dev-server")){
              this.todoItems.push(JSON.parse(localStorage.getItem(localStorage.key(i))));
        }
      }
    }
  },
  components : {
    'Todo-Header' : TodoHeader,
    'Todo-Input' : TodoInput,
    'Todo-List' : TodoList,
    'Todo-Footer' : TodoFooter
  }
}
</script>

<style>
  body {
    text-align: center;
    background-color: #f6f6f6;
  }

  input {
    border-style: groove;
    widows: 200px;
  }

button {
  border-style: groove;
}
.shadow {
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
}

</style>