<template>
    <h1>Creating tasks</h1>
    <form>
        <div class="form_element">
            <input v-model="taskName" type="text" placeholder="name task"/>
        </div>
        <div class="form_element">
            <textarea v-model="taskDescription" placeholder="task description">

            </textarea>
        </div>
        <div class="form_element">
            <button @click="onSubmit" type="button">Create</button>
        </div>
    </form>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'AddTaskView',
    data() {
        return {
            taskName: '',
            taskDescription: ''
        }
    },

    methods: {
        onSubmit() {
            console.log(this.taskName, this.taskDescription);
            
        }
    },
})
</script>

<style scoped>
.form_element {
    margin: 10px 0;
}
</style>