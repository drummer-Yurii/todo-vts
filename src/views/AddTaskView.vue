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
import { defineComponent } from 'vue';
import { mapMutations } from 'vuex';
import { Task } from '@/types/storeType';

export default defineComponent({
    name: 'AddTaskView',
    data: function() {
        return {
            taskName: '',
            taskDescription: ''
        }
    },

    methods: {
        ...mapMutations(['addTask']),
        onSubmit() {
            const id = (new Date()).getTime();
            const newTask: Task = {
                id: id,
                name: this.taskName,
                description: this.taskDescription
            } 
            this.addTask(newTask);
            
            this.$router.push(`/task/${id}`);
        }
    },
})
</script>

<style scoped>
.form_element {
    margin: 10px 0;
}
</style>