<template>
  <div class="container p-2 text-center">
    <app-header :quoteCount="Quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="Quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row m-2">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info text-danger">
          Info: Please click on quote to delete it!
        </div>
      </div>
    </div>
    <footer class="footer text-center text-muted text-primary">
      Created by <a href="https://github.com/rahulgoyal8312">RG</a>
    </footer>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
  name: 'app',
  components: {
    'appQuoteGrid': QuoteGrid,
    'appNewQuote': NewQuote,
    'appHeader': Header,
  },
  data: function(){
    return {
      maxQuotes: 10,
      Quotes: [
        'A quote to start with something'
      ]
    }
  },
  methods: {
    newQuote(quote){
      if(this.Quotes.length > 9){
        return alert('Please delete a quote, max limit reached!');
      }
      this.Quotes.push(quote);
    },
    deleteQuote(index){
      this.Quotes.splice(index,1);
    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
