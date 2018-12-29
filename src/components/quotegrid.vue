<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" v-bind:key=quote.key @click.native="deletequote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
import Quote from "./quote.vue";

export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deletequote(index) {
      this.$emit("quotedeleted", index);
    }
  }
};
</script>

<style>
</style>