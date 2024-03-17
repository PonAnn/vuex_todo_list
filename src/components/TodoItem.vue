<template>
    <div>
      <ul class="todoList">
        <li class="todo">
          <div class="item">
            <div>
              
              <span :class="{completed: todo.completed}" @click="toggleTodoStatus">{{ todo.title }}</span>
            </div>
            <div>
              <button class="edit"  @click="toggleTodoStatus()">編輯</button>
              <button class="delete" @click="deleteTodo()">刪除</button>  <!--編輯也有刪除線！-->
            </div>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
    export default {
      props:["todo"],

      methods: {
        deleteTodo(){
            this.$store.dispatch("deleteTodo", this.todo);
        },

        toggleTodoStatus() {
            this.$store.dispatch("toggleTodoStatus", this.todo);
        }
      }
    }
</script>

<style scoped>
    ul {
        
        padding-left:0;
    }

    .todoList {
        margin-top:25px;
    }

    .item {
        display:flex;
        justify-content:space-between;
    }

    .edit, .delete {
        font-size:15px;
        margin-left:10px;
        border-radius:50px;
    }

    .completed {
        text-decoration: line-through;
    }

    

</style>