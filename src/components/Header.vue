<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @toggle-add="$emit('toggle-add')" :text="showAddTodo ? 'Close': 'add to-do'" color="blue"/>
    </header>
</template>

<script lang="ts">
import Button from './Button.vue'
export default{
    name: 'Header',
    props: {
        title: String,
        showAddTodo: Boolean,
    },
    components:{
        Button,
    }
}
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;

}
</style>