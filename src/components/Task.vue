<template>
  <div class="tasks" :class="theme !== 'light' ? 'tasks-dark' : ''">
    <div class="task">
    <p class="text">
        {{task.text}}
    </p>
    <p class="day">   
        {{task.day}}
    </p>
    </div>
    <!-- <router-link :to="`/edit/${task.id}`" class="edit">edit</router-link> -->
    <i @click="$emit('delete-task', task.id)" class="fas fa-solid fa-trash"></i>
  </div>
</template>

<script>
export default {
    components: {
        
    },
    props: {
        task: Object,
        theme: String
    }
}
</script>

<style scoped>
.tasks {
    display: grid;
    align-items: center;
    justify-items: center;
    /* grid-template-columns: 2fr 1fr 0.5fr; */
    grid-template-columns: 1fr 1fr;
    /* background-color: rgb(226, 221, 221); */
    margin-bottom: 1em;
    padding: 1em;
    padding-right: 2em;
    border-radius: 0.8em;
    border: 1px solid black;
    /* cursor: pointer; */
}

.tasks-dark {
    border: 1px solid white;
}

.text {
    font-size: 1em;
    font-weight: bold;
}

.day {
    font-size: 0.9em;
}

.task {
    justify-self: start;
}

/* .edit {
    justify-self: center;
    font-size: 0.9em;
    cursor: pointer;
} */

.fas {
  font-size: 0.9em;
  cursor: pointer;
  justify-self: end;
}

.edit {
    color: black;
    text-decoration: none;
}

</style>