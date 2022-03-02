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
            currentData: []
        }
    },
    components: {
        EditTask
    },
    methods: {
        // fetchTask(id) {
        //     fetch(`api/tasks/${id}`)
        //         .then(response => response.json())
        //         .then(res => {
        //             this.currentData = res
        //         })
        // }
    },
    // async mounted () {
    //     await this.fetchTask (this.$route.params.id)
    //     console.log(this.currentData)
    // }
}
</script>

<style scoped>
.back {
    color: black;
}
</style>