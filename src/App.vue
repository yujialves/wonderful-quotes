<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <quote-form @addQuote="addQuote"></quote-form>
    <quote-container :quotes="quotes" @deleteQuote="deleteQuote"></quote-container>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteContainer from "./components/QuoteContainer.vue";
import QuoteForm from "./components/QuoteForm.vue";
import Header from "./components/Header.vue";
export default {
  data() {
    return {
      quotes: ["Hello World!!!"],
      maxQuotes: 10,
    };
  },
  methods: {
    addQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete Quotes first!");
      }
      this.quotes.push(quote);
    },
    deleteQuote(idx) {
      this.quotes.splice(idx, 1);
    },
  },
  components: {
    QuoteContainer,
    QuoteForm,
    appHeader: Header,
  },
};
</script>

<style>
</style>
