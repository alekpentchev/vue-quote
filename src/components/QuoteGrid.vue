<template>
    <div>
        <app-quote @deleteQuote="deleteQuote" v-for="(quote,index) in quotes" :key="index" :quoteText="quote"/>
    </div>
</template>

<script>
import Quote from './Quote.vue'

    export default {
        props: ['quotes'],
        components: {
            'appQuote': Quote
        },
        methods: {
            deleteQuote(quote) {
                this.$emit('deleteQuote' , quote )
            }
        }
    
    
    
    }
</script>

<style scoped>
    div {
        display: flex;
        justify-content: center;
        margin-top: 40px;
        flex-wrap: wrap;
    }
</style>
