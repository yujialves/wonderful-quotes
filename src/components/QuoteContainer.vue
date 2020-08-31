<template>
  <div>
    <div class="row">
      <quote v-for="(quote, idx) in quotes" :key="idx" @click.native="deleteQuote(idx)">{{ quote }}</quote>
    </div>
  </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
  props: {
    quotes: Array,
  },
  components: {
    Quote,
  },
  methods: {
    deleteQuote(idx) {
      this.$emit("deleteQuote", idx);
    },
  },
};
</script>

<style scoped>
</style>