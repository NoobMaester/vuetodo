<template>
    <header>
        <h1>{{ title }}</h1>
        <Button text="Add to-do" color="blue"/>
    </header>
</template>

<script lang="ts">
import Button from './Button.vue'
export default{
    name: 'Header',
    props: {
        title: String,
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