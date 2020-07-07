<template>
  <div class="container">
    <app-header :quotesNo="quotes.length" :maxquotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="NewQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @quoteDelete="deleteQuote"></app-quote-grid>
    <div class="col-sm-12 text-center">
      <div class="alert alert-info"> Info: Click on a Quote to delete it!</div>

    </div>

    
  </div>
</template>
<script>
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
import Header from "./components/Header";
export default {
  data:function(){
    return{
      quotes:['A quote to see somethings'],
      maxQuotes:10
    }
  },
  methods:{
    NewQuote(quote){
  
      if(this.quotes.length<10){
        this.quotes.push(quote);}else{
alert('soory')
        }
        


      

      

      

    },
    deleteQuote(i){
      this.quotes.splice(i,1);

    }
  }
  ,
  components:{
    appQuoteGrid:QuoteGrid,
    appNewQuote: NewQuote,
    appHeader:Header
  }
}
</script>

<style lang="scss">

</style>
