<template>
  <div class="row">
    <!--dokolku sakame da poslusame event na root component-ot mora da koristeme native-->
    <app-quote v-for="(quote, index) in quotesOk" @click.native="deleteQuote(index)"> {{quote}}</app-quote>
  </div>
</template>

<script>

  import Quote from './Quote.vue'
  export default {
    // vo props gi prenesuvame elementite od nadvor(data f-jata koja vraca objekt)-od root component-ot
    //quotesOk e imeto na data atributot vo tagot  kade  ja zadavame nizata quotes kako vrednost
    props: ['quotesOk'],

    components: {
      appQuote: Quote

    },

    methods: {

      deleteQuote(index) {

       // this.quotesOk.splice(index,1);
          //emitirame event do parent component-ot(go emitirame index-ot)
        this.$emit('quoteDeleted',index);
      }
    }



  }

</script>

<style>


</style>




