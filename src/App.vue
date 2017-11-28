<template>
  <div class="container">

    <app-header :quoteCount="quotes.length" :maxCount="maxQuotes"></app-header>


    <!--go prifacame emitiraniot event od child component-ot NewQuote i ja egzekutirame newQuote f-jata kako rezultat na prifacanjeto od cild-ot-->
    <app-new-quote @quoteAdded="newQuote"> </app-new-quote>
    <!--go prifacame emitiraniot event od child component-ot i regirame na nego vo f-ja-->
   <app-quote-grid :quotesOk="quotes" @quoteDeleted="quoteDeleted"></app-quote-grid>

    <div class="col-sm-12 text-center">
      <div class="alert alert-info">Info:Click on a quote to delete it!</div>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue';
  import NewQuote from './components/NewQuote.vue';
  import Header from './components/Header.vue';
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
      appNewQuote: NewQuote,
      appHeader: Header
    },

    methods: {
      //so ovaa f-ja go dodavame noviot quote
      newQuote(quote){
        // ako brojot na quotes e poholem od maximalniot se pojavuva poraka i izleguvame od f-jata
        if (this.quotes.length >= this.maxQuotes) {
         return alert("Please delete quote! Maximum allowed is 10");
        }
        if (quote !== '') {
            this.quotes.push(quote.trim());
          }

      },


      //index-ot od child component-ot avtomatski e vo argumentot
      quoteDeleted(index) {
        this.quotes.splice(index,1);
      }
    }

  }
</script>

<style>
</style>
