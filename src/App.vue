<template>
    <div class="container">
    
        <div class="row">
            <appHeader :quoteAmount="quoteAmount" :quoteMaxAmount="quoteMaxAmount" />
        </div>
    
        <div class="row">
            <new-quote @increaseQuoteAmount="increaseQuoteAmount" />
        </div>
    
        <div class="row">
            <quote-grid @deleteQuote="deleteQuote" :quotes="quotes" />
        </div>
    
        <hr>

        <div class="jumbotron">
            <p>Click a quote to delete it</p>
        </div>
    
    </div>
</template>

<script>
    import Header from './components/Header.vue'
    import NewQuote from './components/NewQuote.vue'
    import QuoteGrid from './components/QuoteGrid.vue'
    
    export default {
        components: {
            QuoteGrid,
            appHeader: Header,
            NewQuote
        },
        created() {
            if(localStorage.getItem('quotes') != null) {
                this.quotes = JSON.parse(localStorage.getItem('quotes'));
            }
        },
        data() {
            return {
                quoteAmount: 1,
                quoteMaxAmount: 10,
                quoteText: '',
                quotes: [
                    'Example quote'
                ],
            }
        },
        methods: {
            increaseQuoteAmount(quote) {
                if (this.quoteAmount < this.quoteMaxAmount) {
                    this.quoteAmount += 1
                    this.quotes.push(quote)

                    localStorage.setItem('quotes' , JSON.stringify(this.quotes))
                }
            },
    
            deleteQuote(quote) {
                this.quoteAmount -= 1
                this.quotes.splice(quote, 1)
                
                localStorage.setItem('quotes' , JSON.stringify(this.quotes))
            }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css?family=Amatic+SC|Raleway');
    .form-area {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-family: 'Raleway', sans-serif
    }
    
    .progress {
        height: 30px;
        font-family: 'Raleway', sans-serif
    }
    
    .progress-bar {
        /* width: 70%; */
        font-size: 2rem;
        line-height: 150%
    }

    .jumbotron {
        text-align: center;
    }
</style>
