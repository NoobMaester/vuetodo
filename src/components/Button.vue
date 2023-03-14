<template>
  <button @click="onClick" class="btn">{{ text }}</button>
</template>

<script lang="ts">
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick(){
      this.$emit('toggle-add')
      console.log('cliick!')
    }
  }
};
</script>
