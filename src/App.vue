<template>  
<div id="app">
  <Todos :p_todos="todos" @emDelTodo2="deleteTodo"/>
</div>
</template>

<script>
import Todos from './components/Todos'

  export default {
    name: 'App',
    components: {
      Todos
    },
    data(){
      return {
        todos: [
        {
          id: 1,
          title: 'Todo One',
          completed: false
        },
        {
          id: 2,
          title: 'Todo Two',
          completed: true
        },
        {
          id: 3,
          title: 'Todo Three',
          completed: false
        }
        ]
      }
    },
    methods: {
      deleteTodo(id){
        this.todos = this.todos.filter(todos => todos.id !== id)
      }
    }
  }
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvatica, sans-serif;
  line-height: 1.4;
}
</style>
