<template>
    <div class="header">
            <div class="progress__container">
                <div class="progress__box">
                    <div class="progress__bar" role="progressbar" 
                        :style="{width: (taskCount / archiveCount) * 100 + '%'}">
                       <p class="counters"> {{ taskCount || '-' }} / {{ archiveCount || '-'}}</p>
                    </div>
                </div>
            </div>
    </div>
</template>
<script>
    export default {
        props: ['taskCount', 'archiveCount']
    }
</script>