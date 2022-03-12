<template>
    <router-link to="/" class="back">Go Back</router-link>
    <EditTask />
</template>

<script>
import EditTask from '../components/EditTask.vue'
export default {
    inheritAttrs: false,
    data () {
        return {
            currentData: null
        }
    },
    components: {
        EditTask
    },
    methods: {
        async fetchTask(id) {
            const res = await fetch(`api/tasks/${id}`)
            console.log('response:', res)
            const data = await res.json()
            console.log(data)
            return data
        }
    },
    async mounted () {
        console.log(this.$route.params.id)
        this.currentData = await this.fetchTask(1)
        // console.log(this.currentData)
    }
}
</script>

<style scoped>
.back {
    color: black;
}
</style>