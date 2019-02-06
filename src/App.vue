<template>
    <div class="main__container">
        <section class="form__box">
        <app-header :taskCount="tasks.length" :archiveCount="archives.length" ></app-header>
        <app-new-task @taskAdded="newTask"></app-new-task>
        </section>
        <h2>Tasks:</h2>
        <app-task-grid :tasks="tasks" @archivedTask="archiveTask"></app-task-grid>
        <h2>Done tasks:</h2>
        <app-archive-grid :archives="archives" @deleteArchive="deleteArchive"></app-archive-grid>
    </div>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue'
import ArchiveGrid from './components/ArchiveGrid.vue'
import NewTask from './components/NewTask.vue'
import Header from './components/Header.vue'

export default {
  data: function () {
    return {
      tasks: [],
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
    appHeader: Header
  }
}
</script>

<style>
  @import './assets/styles/base.css';
</style>
