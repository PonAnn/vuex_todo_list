<template>
    <TodoItem v-for="(todo, index) in todos" :key="index" :todo="todo"></TodoItem>
</template>

<script>
    import TodoItem from "./TodoItem"

    export default {
        name:"TodoList",
        components:{
            TodoItem
        },

        computed: {
            todos(){
                return this.$store.state.todos;
            }
        }
    }
</script>

<style scoped>
    .nav {
        display:flex;
    }

    .navIcon {
        margin-right:10px;
    }

    hr{
        width:100%;
        margin:20px 0px;
    }

</style>