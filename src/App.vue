<template>
  <div id="app">
    <Header />
    <Products v-bind:products="products" />
  </div>
</template>

<script>
import Header from "./components/layouts/Header.vue";
import Products from "./components/Products.vue";
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "App",
  components: {
    Header,
    Products
  },
  data() {
    return {
      products: []
    };
  },
  created() {
    Vue.axios
      .get(
        "https://8efa2bba-05f2-45a9-b3dd-ef310fcade7b.mock.pstmn.io/shoppable"
      )
      .then(res => (this.products = res.data))
      .catch(err => console.log(err));
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
