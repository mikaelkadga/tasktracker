<template>
    <AddTask @add-task="addTask" v-show="showAddTask"/>
    <Tasks :theme="theme" @delete-task="deleteTask" @edit-task="editTask" :tasks="tasks"/>
</template>

<script>
import Tasks from '../components/Tasks.vue'
import AddTask from '../components/AddTask.vue'

export default {
    components: {
        Tasks,
        AddTask
    },
    data () {
        return {
            tasks: []
        }
    },
    props: {
        showAddTask: Boolean,
        theme: String
    },
    methods: {
        async addTask (task) {
            const res = await fetch('api/tasks', {
                method: 'POST',
                headers: {
                    'Content-type': 'application/json'
                },
                body: JSON.stringify(task) 
            })

            const data = await res.json()

            this.tasks = [...this.tasks, data]
        },
        async deleteTask (id) {
            if(confirm('really?')) {
                const res = await fetch(`api/tasks/${id}`, {
                    method: 'DELETE',
                })

                res.status === 200 ? (this.tasks = this.tasks.filter((task) => task.id !== id)) : alert('error deleting task')
            }   
        },
        editTask (id) {
            console.log(id)
        },
        async fetchTasks() {
            const res = await fetch('api/tasks')
            const data = await res.json()
            return data
        }
    },
    async created () {
        this.tasks = await this.fetchTasks()
    }
}
</script>

<style scoped>
h1 {
    font-family: inherit;
}
</style>