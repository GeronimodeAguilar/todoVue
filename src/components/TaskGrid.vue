<template>
    <div class="task__box">
      <h2>Tasks:</h2>
        <app-task v-for="(task, index) in tasks" @click.native="archiveTask(task, index)">{{ task }}</app-task>
    </div>
</template>

<script>
import Task from './Task.vue'

export default {
  props: ['tasks'],
  components: {
    appTask: Task
  },
  methods: {
    archiveTask (task, index) {
      this.$emit('archivedTask', task, index)
    }
  }
}
</script>

<style>

</style>
