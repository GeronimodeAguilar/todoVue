<template>
        <form>
            <div class="quote__form">
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
            <div class="quote__add">
               <button class="add__button" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
</template>

<script>
    export default {
        data: function() {
            return {
                quote: ''
            };
        },
        methods: {
            createNew() {
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>

</style>