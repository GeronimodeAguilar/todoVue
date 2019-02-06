<template>
            <div class="task__form">
        <form class="text__form">
                <textarea class="form-control" rows="2" v-model="task"></textarea>
        </form>
            <div class="task__add">
               <button class="add__button" @click.prevent="createNew">Add</button>
            </div>
            </div>
</template>

<script>
export default {
  data: function () {
    return {
      task: ''
    }
  },
  methods: {
    createNew () {
      this.$emit('taskAdded', this.task)
      this.task = ''
    }
  }
}
</script>

<style>

</style>
