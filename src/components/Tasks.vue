<template>
  <div v-for="task in tasks" :key="task.id">
      <Task :theme="theme" @delete-task="$emit('delete-task', task.id)" @edit-task="$emit('edit-task', task.id)" :task="task"/>
  </div>
</template>

<script>
import Task from './Task.vue'
export default {
    components: {
        Task
    },
    props: {
        tasks: Array,
        theme: String
    },
    emits: [
        'delete-task',
        'edit-task'
    ]
}
</script>

<style>

</style>