<template>
  <div id="app">
    <Todo-Header1></Todo-Header1>
    <Todo-Input1></Todo-Input1>
    <Todo-List1></Todo-List1>
    <Todo-Footer1></Todo-Footer1>

  </div>
</template>

<script>

import TodoHeader1 from "./components/TodoHeader1.vue"
import TodoInput1 from "./components/TodoInput1.vue"
import TodoList1 from "./components/TodoList1.vue"
import TodoFooter1 from "./components/TodoFooter1.vue"

export default {
  components : {
    "Todo-Header1" : TodoHeader1,
    "Todo-Input1" : TodoInput1,
    "Todo-List1" : TodoList1,
    "Todo-Footer1" : TodoFooter1
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