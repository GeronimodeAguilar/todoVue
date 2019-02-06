<template>
    <div class="main__container">
        <app-percentage :taskCount="tasks.length" :archiveCount="archives.length" ></app-percentage>
        <section class="front__box">
        <section class="form__box">
        <app-new-task @taskAdded="newTask"></app-new-task>
        </section>
        <app-task-grid :tasks="tasks" @archivedTask="archiveTask"></app-task-grid>
        <app-archive-grid :archives="archives" @deleteArchive="deleteArchive"></app-archive-grid>
        </section>
    </div>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue'
import ArchiveGrid from './components/ArchiveGrid.vue'
import NewTask from './components/NewTask.vue'
import Percentage from './components/Percentage.vue'

export default {
  data: function () {
    return {
      tasks: ['10 pull-ups', '10 000 steps', '20 push-ups', '50 sit-ups'],
      archives: []
    }
  },
  methods: {
    newTask (task) {
      this.tasks.push(task)
    },
    archiveTask (task, index) {
      this.tasks.splice(index, 1)
      this.archives.push(task)
    },
    deleteArchive (index) {
      this.archives.splice(index, 1)
    }
  },
  components: {
    appTaskGrid: TaskGrid,
    appArchiveGrid: ArchiveGrid,
    appNewTask: NewTask,
    appPercentage: Percentage
  }
}
</script>

<style>
  @import './assets/styles/base.css';
</style>
