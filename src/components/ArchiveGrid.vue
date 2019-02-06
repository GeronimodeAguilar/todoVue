<template>
    <div class="archive__box">
      <h2>Done tasks:</h2>
        <app-archive v-for="(archive, index) in archives" @click.native="archiveTask(index)">{{ archive }}</app-archive>
    </div>
</template>

<script>
import Archive from './Archive.vue'

export default {
  props: ['archives'],
  components: {
    appArchive: Archive
  },
  methods: {
    archiveTask (index) {
      this.$emit('deleteArchive', index)
    }
  }
}
</script>

<style>

</style>
