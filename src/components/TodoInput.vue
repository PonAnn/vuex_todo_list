<template>
    <div>
      <input class="addTodo" type="text" size="40" placeholder="要新增的任務" v-model="newTodoItem" @keyup.enter="addNewTodoItem">
      <button class="add" @click="addNewTodoItem()">+</button>
    </div>
    <hr/>
</template>

<script>
    export default {
       data(){
        return {
            newTodoItem: ""
        };
       },

       methods: {
        addNewTodoItem() {
            this.$store.dispatch("addNewTodo",this.newTodoItem);
            this.newTodoItem="";
        }
       }
    }
</script>

<style scoped>
    .addTodo {
        font-size:18px;
        padding:10px;
        border-radius:20px;  
    }

    .add {
        font-size:20px;
        margin-left:10px;
        border-radius:50px;
    }

    hr{
        width:100%;
        margin:20px 0px;
    }
</style>