<template>
    <div @click="onQuoteDelete" class="col-md-3 card">
        <div class="card-desc">
            <p>{{quoteText}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['quoteText'],
        methods: {
            onQuoteDelete() {
                this.$emit('deleteQuote' , this.quoteText)
            }
        }
    }
</script>

<style scoped>
    .card {
        min-height: 140px;
        margin: 10px;
        border-radius: 5px;
        border: 1px solid lightgray;
        font-size: 3.5rem;

        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }

    .card-desc {
        font-family: 'Amatic SC', cursive;
        text-align: center;
    }

    .card:hover {
        background-color: lightcoral;
        color: white;
        cursor: pointer;
    }
</style>
