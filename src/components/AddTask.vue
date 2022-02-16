<template>
   <div>
       <form @submit="onSubmit">
           <div class="form">
               <label>task</label>
               <input type="text" v-model="text" name="text" placeholder="task">
           </div>
           <div class="form">
               <label>day and time</label>
               <input type="text" v-model="day" name="day" placeholder="day and time">
           </div>
           <input type="submit" value="save task" class="btn">
       </form>
   </div>
</template>

<script>
export default {
    data () {
        return {
            text: '',
            day: ''
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()

            if(!this.text) {
                alert('add a task, please')
            }

            const newTask = {
                // id: Math.floor(Math.random() * 1000),
                text: this.text,
                day: this.day
            }

            this.$emit('add-task', newTask)
            // console.log(newTask)

            this.text = ''
            this.day= ''
        }
    }
}
</script>

<style scoped>
.form {
    display: flex;
    flex-direction: column;
    font-size: 1rem;
    margin: 1em 0;
}

.form input {
    border: solid 1px black;
    border-radius: 0.3em;
    padding: 0.5em;
    font-size: 1rem;
}

.btn {    
    padding: 0.7em;
    background: black;
    color: white;
    border: none;
    border-radius: 0.8em;
    cursor: pointer;
    font-family: inherit;
    width: 100%;
    margin-bottom: 1.4em;
}
</style>