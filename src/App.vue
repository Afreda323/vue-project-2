<template>
    <div class="container">
        <app-header :count="count" :max="max" />
        <div class="row">
            <app-quote-input :onSubmit="addQuote" />
        </div>
        <br />
        <div class="row">
            <app-quote 
                v-if="quotes.length"
                v-for="quote in quotes"
                :key="quote.id"
                :onDelete="deleteQuote"
                :quote="quote" />
        </div>
        <p class="text-center">
          <small class="text-primary" v-show="quotes.length">
            Click a quote to delete it
          </small>
        </p>
    </div>
</template>

<script>
import AppHeader from './components/Header.vue'
import AppQuoteInput from './components/QuoteInput.vue'
import AppQuote from './components/Quote.vue'

export default {
  data() {
    return {
      max: 10,
      quotes: [],
    }
  },
  computed: {
    count() {
      return this.quotes.length
    },
  },
  methods: {
    addQuote(text) {
      if (this.quotes.length + 1 > this.max) {
        alert('Too many quotes, delete one to add another')
      } else if (text.length) {
        this.quotes.push({ text, id: Date.now() })
      }
    },
    deleteQuote(id) {
      const filtered = this.quotes.filter(quote => quote.id !== id)
      this.quotes = filtered
    },
  },
  components: {
    AppHeader,
    AppQuoteInput,
    AppQuote,
  },
}
</script>

<style>

</style>
