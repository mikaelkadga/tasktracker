<template>
  <div class="tasks">
    <div class="task">
    <p class="text">
        {{task.text}}
    </p>
    <p class="day">   
        {{task.day}}
    </p>
    </div>
    <p class="edit">edit</p>
    <i @click="$emit('delete-task', task.id)" class="fas fa-solid fa-trash"></i>
  </div>
</template>

<script>
export default {
    components: {
        
    },
    props: {
        task: Object
    }
}
</script>

<style scoped>
.tasks {
    display: grid;
    align-items: center;
    justify-items: center;
    grid-template-columns: 2fr 1fr 0.5fr;
    background-color: rgb(226, 221, 221);
    margin-bottom: 1em;
    padding: 1em;
    border-radius: 0.8em;
    /* cursor: pointer; */
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

.edit {
    justify-self: center;
    font-size: 0.9em;
    cursor: pointer;
}

.fas {
  font-size: 0.9em;
  cursor: pointer;
}

</style>