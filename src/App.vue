<template>
  <div class="container">
    <app-header :maxQuotes="maxQuotes" :quotes="quotes"></app-header>
    <app-new-quote :maxQuotes="maxQuotes" :quotes="quotes" @quoteAdded="addQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on a Quote to delete it.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data () {
    return {
      maxQuotes: 10,
      quotes: [ "Just to see something." ]
    }
  },
  methods: {
    addQuote(quote) {
      if(this.quotes.length >= this.maxQuotes) {
        return alert('You have reached the maximum amount of Quotes added. Please delete a Quote before you can add a new Quote');
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  }
}
</script>

<style>
</style>
