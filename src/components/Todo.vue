<template>
    <div class="todo">
        <h3>{{ this.todo.title }}</h3>
        <p>{{ this.todo.day }}</p>
    </div>
</template>

<script lang="ts">
export default{
    name: 'Todo',
    props: {
        todo: Object,
    }
}
</script>

<style scoped>
.todo{
    border: 1px solid crimson;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}
.todo h3{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.todo.reminder{
    border-left: 10px solid crimson;
}
</style>