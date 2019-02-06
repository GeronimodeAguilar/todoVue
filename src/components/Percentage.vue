<template>
    <div class="percentage">
                    <div class="progress__bar" role="progressbar"
                        :style="{height: (archiveCount /( archiveCount + taskCount )) * 100 + '%'}">
                       <p class="progress__text"> {{ truncPercentage() + '%'}}</p>
                    </div>
    </div>
</template>
<script>
export default {
  props: ['taskCount', 'archiveCount'],  
  methods: {
    truncPercentage () {
     return Math.trunc((this.archiveCount /( this.archiveCount + this.taskCount ))* 100)  || '0' 
    }
  }
}
</script>

