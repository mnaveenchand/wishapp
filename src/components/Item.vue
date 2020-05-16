<template>
  <div>
    <div v-bind:key="item.productId" v-for="item in items">
      <b-container class="bv-example-row bv-example-row-flex-cols">
        <b-row align-v="start" class="mb-3">
          <b-col md="4" class="ml-md-auto p-3 bg-info">
              {{item.product}}
              <b-button href="#" variant="primary">Addto</b-button>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>
<script>
export default {
  name: "Items",
  props: ["items"]
};
</script>
<style scoped>
</style>