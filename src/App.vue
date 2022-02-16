<template>
  <div class="wrapper">
    <div class="container">
      <Header :showAddTask="showAddTask" @toggle-add-task="toggleAddTask" title="what am i gonna do" />
      <router-view :showAddTask="showAddTask"></router-view>
      <Footer />
    </div>
</div>
  
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer
  },
  data () {
    return {
      showAddTask: false
    }
  },
  methods: {
    toggleAddTask () {
      this.showAddTask = !this.showAddTask
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.wrapper {
  height: 100vh;
  display: flex;
  align-items: center;
}

.container {
  font-size: 14px;
  width: 25em;
  margin: 2em auto;
  padding: 1.3em;
  border: 1px solid black;
  border-radius: 0.3em;
}

@media (min-width:800px) {
  .container {
    width: 32em
  }
}
</style>
