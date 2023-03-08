<template>
  <button @click="onclick" class="btn">{{ text }}</button>
</template>

<script lang="ts">
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onclick(){
      console.log('cliick!')
    }
  }
};
</script>
