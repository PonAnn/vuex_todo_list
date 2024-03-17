<template>
    <div>
        <hr/>
      <div class="total">
        <h3>已完成：{{ $store.getters.completedTodos }} ，
            未完成：{{ $store.getters.pendingTodos }} ，
            全部：{{ $store.getters.totalTodos }}。
        </h3>  
      </div>
    </div>
</template>

<script>
    export default {
      
    }
</script>

<style scoped>
    .total {
        display:flex;
        justify-content:space-between;
    }

    hr{
        width:100%;
        margin:20px 0px;
    }
</style>