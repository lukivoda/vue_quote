<template>
  <div class="container">
    go prifacame emitiraniot event od child component-ot NewQuote i ja egzekutirame newQuote f-jata kako rezultat na prifacanjeto od cild-ot
    <app-new-quote @quoteAdded="newQuote"> </app-new-quote>
   <app-quote-grid :quotesOk="quotes"></app-quote-grid>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue';
  import NewQuote from './components/NewQuote.vue'
  export default {

    data() {
      return {
        quotes:['Just to see something'],

        maxQuotes: 10
      }

    },
//dodavame novi child components
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote
    },

    methods: {
      //so ovaa f-ja go dodavame noviot quote
      newQuote(quote){
        if(quote !== '') {
          this.quotes.unshift(quote.trim());
        }
      }
    }

  }
</script>

<style>
</style>
