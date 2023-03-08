<template>
    <div v-for="todo in this.todos" :key="todo.id">
        <Todo :todo="todo"/>
    </div>
</template>

<script lang="ts">
import Todo from './Todo.vue'

export default{
    name: 'Todos',
    components:{
        Todo,
    },
    props: {
        todos: Array,
    },
}
</script>