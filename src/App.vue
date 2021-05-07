<template>  
<div id="app">
  <Header />
  <AddTodo @em-sendTodo="submitTodo"/>
  <Todos :p_todos="todos" @emDelTodo2="deleteTodo"/>
</div>
</template>

<script>
import Todos from './components/Todos'
import Header from './components/layouts/Header'
import AddTodo from './components/layouts/AddTodo'
import axios from 'axios'

  export default {
    name: 'App',
    components: {
      Todos,
      Header,
      AddTodo
    },
    created(){
      axios.get('https://jsonplaceholder.typicode.com/todos?_limit=20')
            .then(res => this.todos = res.data)
            .catch(err => console.log(err))
    },
    data(){
      return {
        todos: []
      }
    },
    methods: {
      submitTodo(data){
        this.todos.push(data)
      },
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
