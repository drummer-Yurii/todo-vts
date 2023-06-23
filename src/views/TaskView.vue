<template>
    <div>
        <h1>{{ task.name }}</h1>
        <div>{{ task.description }}</div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { mapActions } from 'vuex';
import { Task } from '@/types/storeType';

export default defineComponent({
    name: 'TaskView',
    data: function() {
        return {
            task: {} as Task,
        }
    },

    computed: {
        id() {
            return this.$route.params.id;
        }
    },

    methods: {
        ...mapActions(['getTaskById']),
    },

    async mounted () {
        const task: Task = await this.getTaskById(this.id);

        this.task = task;
    },
})
</script>

<style scoped>

</style>