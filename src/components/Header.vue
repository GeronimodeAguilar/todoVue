<template>
    <div class="header">
            <div class="progress__container">
                <div class="progress__box">
                    <div class="progress__bar" role="progressbar" 
                        :style="{width: (taskCount / maxTasks) * 100 + '%'}">
                       <p class="counters"> {{ taskCount || '-' }} / {{ maxTasks || '-'}}</p>
                    </div>
                </div>
            </div>
    </div>
</template>
<script>
    export default {
        props: ['taskCount', 'maxTasks']
    }
</script>