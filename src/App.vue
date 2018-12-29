<template>
    <div class="container">
      
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
       
      <appheader :quotecount="quotes.length"
      :maxquotes="maxquotes"></appheader>
      <appnewquote @quoteadd="newquotes"></appnewquote>
    <appquotegrid :quotes="quotes" @quotedeleted="deletequote"></appquotegrid>
    <div class="row">
      <div class="col-sm-12 text-center">
<div class="alert alert-info">
  INFO: click on a quote to delete 
</div>
      </div>
    </div>
    </div>
</template>

<script>
import header from "./components/header.vue";
import newquote from "./components/newquote.vue";
import quotegrid from "./components/quotegrid.vue";
export default {
  data: function() {
    return {
      quotes: [
        "This application is completely writtened in vue.js as SPA",
        "component based approach",
        "quotes can ba added to it",
        "delete the quote to click it"
      ],
      maxquotes: 10
    };
  },
  methods: {
    newquotes(quote) {
      if (this.quotes.length >= this.maxquotes) {
        return alert("delete quotes to enter more..!");
      }
      this.quotes.push(quote);
    },
    deletequote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appquotegrid: quotegrid,
    appnewquote: newquote,
    appheader: header
  }
};
</script>

<style>
body {
  background-image: url(https://images.pexels.com/photos/301943/pexels-photo-301943.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260);
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
