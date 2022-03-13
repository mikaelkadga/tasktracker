<template>
  <div :class="theme === 'light' ? 'light-theme' : 'dark-theme'" class="wrapper">
    <div>
      <div @click="changeTheme" class="theme-toggle">
        <i class="bi bi-moon-fill moon"></i>
        <i class="bi bi-brightness-high-fill sun"></i>
        <i class="ball" :class="theme === 'light' ? 'ball-dark' : ''"></i>
      </div>
    </div>
    <div class="container" :class="theme === 'light' ? '' : 'container-dark'">
      <Header :theme="theme" :showAddTask="showAddTask" @toggle-add-task="toggleAddTask" title="what am i gonna do" />
      <router-view :theme="theme" :showAddTask="showAddTask"></router-view>
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
      showAddTask: false,
      theme: "light"
    }
  },
  methods: {
    toggleAddTask () {
      this.showAddTask = !this.showAddTask
    },
    changeTheme () {
      console.log("changing theme")
      this.theme = this.theme === "dark" ? "light" : "dark"
      console.log(this.theme)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.1/font/bootstrap-icons.css");

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
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.container {
  font-size: 14px;
  width: 25em;
  margin: 2em auto;
  padding: 1.3em;
  border: 1px solid black;
  border-radius: 0.3em;
}

.container-dark {
  border: 1px solid white;
}

.theme-toggle {
  width: 60px;
  height: 30px;
  padding: 0.5em;
  background-color: black;
  border-radius: 25px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
  cursor: pointer;
}

.moon {
  color: white;
  /* cursor: pointer; */
}

.sun {
  color: orange;
  /* cursor: pointer; */
}

.ball {
  height: 20px;
  width: 20px;
  background-color: white;
  border-radius: 50%;
  position: absolute;
  cursor: pointer;
  transition: 300ms;
}

.ball-dark {
  transform: translateX(25px);
}

.light-theme {
  background-color: rgb(245, 239, 239);
  color: black;
  transition: 300ms;
}

.dark-theme {
  background-color: #192734;
  color: white;
  transition: 300ms;
}

@media (min-width:800px) {
  .container {
    width: 32em
  }
}
</style>
