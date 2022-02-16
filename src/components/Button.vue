<template>
  <button :style="{background: color}" @click="$emit('btn-click')">
      {{text}}
  </button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String
    },
    methods: {
        onClick() {
            console.log("Clicked")
        }
    }
}
</script>

<style scoped>

button {    
    padding: 0.5em;
    font-size: 0.8em;
    font-weight: 600;
    background: black;
    color: white;
    border: none;
    border-radius: 0.8em;
    cursor: pointer;
    font-family: inherit;
}
</style>