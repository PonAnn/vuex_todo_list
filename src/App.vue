<template>
  <div class="all">
    <h1>Todo List</h1>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
    
    
  </div>
</template>

<script>
  import TodoInput from "./components/TodoInput"
  import TodoList from "./components/TodoList"
  import TodoFooter from "./components/TodoFooter.vue"


  export default {
    name: 'App',
    components: {
      TodoInput,
      TodoList,
      TodoFooter
    },

    computed: {
      computedTodos(){
        return this.$store.getters.completedTodos
      },
      pendingTodos(){
        return this.$store.getters.pendingTodos
      },
      totalTodos(){
        return this.$store.getters.totalTodos
      }
    }
  }
</script>

<style>
  .all {
    margin:0 auto;
    max-width:500px;
  }

  h1 {
    text-align:center;
    font-size:50px;
  }
</style>
