<template>
  <div class="row">
    <app-quote v-for="quote in quotesOk"> {{quote}}</app-quote>
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

    }

  }

</script>

<style>


</style>




