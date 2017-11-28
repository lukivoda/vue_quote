<template>
  <form >
  <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
    <label>Quote</label>
    <!--double binding funkcionalnst na quote-->
    <textarea class="form-control" rows="3" v-model="quote"></textarea>
  </div>

    <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <!--prevent go stavame za da  ne probuva da ja submitira formata(oti toa ne ni treba)-->
      <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
    </div>

  </form>
</template>

<script>

  export default {

    data() {
      return {
        quote: ''
      }

    },methods: {
        createNew() {
          //go emitirame content-ot od formata do parent component
          this.$emit('quoteAdded',this.quote);
          //ja praznime text area-ta
          this.quote = '';

        }

    }
  }

</script>

<style>

</style>
