<template>
  <!-- <div>
    <div v-bind:key="product.categoryId" v-for="product in products"> -->
      <!-- <div class="mb-3">
        <b-button v-b-toggle="product.category">{{product.category}}</b-button>
      </div>
      <b-collapse id="product.category">
        <Items v-bind:items="product.items" />
      </b-collapse>-->
      <div>
        <b-card no-body class="mb-1"  v-bind:key="product.categoryId" v-for="product in products">
          <b-card-header header-tag="header" class="p-1" role="tab">
            <b-button block v-b-toggle="'accordion'+product.categoryId" variant="info">{{product.category}}</b-button>
          </b-card-header>
          <b-collapse :id="'accordion'+categoryId" visible accordion="my-accordion">
            <b-card-body>
              <Items v-bind:items="product.items" />
            </b-card-body>
          </b-collapse>
        </b-card>
      </div>
   <!--  </div>
  </div> -->
</template>
<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";
import Items from "./Item";

Vue.use(VueAxios, axios);

export default {
  name: "Products",
  props: ["products"],
  components: {
    Items
  },
  created() {}
};
</script>
<style scoped>
</style>
