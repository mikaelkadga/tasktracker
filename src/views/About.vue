<template>
  <h3>Version 1.0.0</h3>
  <router-link to="/" class="back">Home</router-link>
</template>

<script>
export default {
    inheritAttrs: false,
    props: {
        showAddTask: Boolean
    }
}
</script>

<style scoped>
.back {
    color: black;
}

</style>