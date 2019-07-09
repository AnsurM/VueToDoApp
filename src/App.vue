<template>
  <div>
    <TodoList v-bind:todos="todos"></TodoList>
    <create-todo v-on:create-todo="addTodo"></create-todo>
  </div>
</template>

<script>
import TodoList from './components/ToDoList'
import CreateTodo from './components/CreateTodo'

/* eslint-disable */
export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        title: title.title,
        project: title.project,
        done: false
      });
    },
  },
  
  data () {
      let todos = [
        {
          title: 'Todo A',
          project: 'Project A',
          done: false
        },
        {
          title: 'Todo B',
          project: 'Project B',
          done: true
        },
        {
          title: 'Todo C',
          project: 'Project C',
          done: false
        },
        {
          title: 'Todo D',
          project: 'Project D',
          done: false
        }
      ];
      return {
        todos
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
