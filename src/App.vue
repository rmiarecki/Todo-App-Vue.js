<template>
  <div class="container">
    <h1>TODO APP</h1>
    <ToDoApp />
  </div>
</template>


<script>
import Todo from './components/ToDoApp.vue'
import './assets/styles/style.css'

export default {
  components: {
    ToDoApp: Todo
  }
}
</script>