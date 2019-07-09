<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => todo.done === true).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => todo.done === false).length}}</p>
    <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo" v-for="todo in todos" :key='todo.id' v-bind:todo="todo"></todo>
  </div>
</template>

<script type="text/javascript">
/*eslint-disable*/
import Todo from './ToDo'

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    deleteTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos.splice(todoIndex, 1)
    },
    completeTodo(todo) {
      console.log("Todo is: ", todo);
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    }    
  }
}
</script>

<style>
</style>
