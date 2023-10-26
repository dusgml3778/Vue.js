<template>
  <div id="app">
    <Todo-Header></Todo-Header>
    <Todo-Input></Todo-Input>
    <Todo-List></Todo-List>
    <Todo-Footer></Todo-Footer>
  </div>
</template>

<script>

import TodoHeader from './components/TodoHeader.vue'
import TodoInput from "./components/TodoInput.vue"
import TodoList from "./components/TodoList.vue"
import TodoFooter from "./components/TodoFooter.vue"

export default {
  components : {
    'Todo-Header' : TodoHeader,
    'Todo-Input' : TodoInput,
    'Todo-List' : TodoList,
    'Todo-Footer' : TodoFooter
  }
}
</script>

<style>

</style>