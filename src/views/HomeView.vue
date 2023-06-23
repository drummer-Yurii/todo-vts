<template>
  <div class="home">
    <div v-for="task in tasks" :key="task.id">
      <h4>
        <router-link :to="`/task/${task.id}`">{{ task.name }}</router-link>
      </h4>
    </div>
    <div v-if="tasks.length === 0">Steel dont have tasks!</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { mapGetters } from 'vuex';
import { Task } from '@/types/storeType';

export default defineComponent({
  name: 'HomeView',
  components: {
    
  },

  data: function() {
    return {
      tasks: [] as Task[]
    }
  },

  methods: {
    ...mapGetters(['getAllTasks'])
  },

  mounted () {
    this.tasks = this.getAllTasks();
  },
});
</script>
