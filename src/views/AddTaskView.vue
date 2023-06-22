<template>
    <h1>Creating tasks</h1>
    <form>
        <div class="form_element">
            <input type="text" placeholder="name task"/>
        </div>
        <div class="form_element">
            <textarea placeholder="task description">

            </textarea>
        </div>
        <div class="form_element">
            <button type="button">Create</button>
        </div>
    </form>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'AddTaskView',
    setup () {
        

        return {}
    }
})
</script>

<style scoped>
.form_element {
    margin: 10px 0;
}
</style>