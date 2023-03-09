<template>
    <div v-for="todo in this.todos" :key="todo.id">
        <Todo @toggle-reminder="$emit('toggle-reminder', todo.id)" @delete-todo="$emit('delete-todo', todo.id)" :todo="todo"/>
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
    emits: ['delete-todo', 'toggle-reminder']
}
</script>