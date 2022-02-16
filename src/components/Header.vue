<template>
    <header>
        <h2>
        {{title}}
        </h2>
        <Button 
        v-show="homePage" 
        @btn-click="$emit('toggle-add-task')" 
        :text="showAddTask ? 'close' : 'add task'"
        :color="showAddTask ? '' : ''" />
    </header>
</template>

<script>
import Button from './Button.vue'
export default {
    name: 'Header',
    components: {
        Button
    },
    props: {
        title: String,
        showAddTask: Boolean
    },
    computed: {
        homePage () {
            if (this.$route.path === '/') {
                return true
            } else {
                return false
            }
        }
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2em;
}
</style>