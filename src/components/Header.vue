<template>
    <div class="header">
            <div class="progress__container">
                <div class="progress__box">
                    <div class="progress__bar" role="progressbar" 
                        :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                        {{ quoteCount }} / {{ maxQuotes}}
                    </div>
                </div>
            </div>
    </div>
</template>
<script>
    export default {
        props: ['quoteCount', 'maxQuotes']
    }
</script>