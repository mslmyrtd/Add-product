<template>
  <div class="container">
    <h1 class="text-center">Add Product App</h1>
    <hr />
    <new-product></new-product>
    <br /><br />
    <app-progress></app-progress>
    <br /><br />
    <h3 class="text-center">Added Product List</h3>
    <hr />
    <app-products></app-products>
  </div>
</template>

<script>
import NewProduct from "./components/NewProduct.vue";
import Progress from "./components/Progress.vue";
import Products from "./components/Products.vue";

export default {
  components: {
    NewProduct,
    appProgress: Progress,
    appProducts: Products,
  },
};
</script>

<style>
body {
  background-color: rgb(135, 187, 233);
  padding-top: 20px;
  padding-bottom: 20px;
}

.card {
  margin-right: 5px;
  margin-bottom: 5px;
}

.card:last-child {
  margin-right: 0px;
}

.col-md-2 {
  max-width: 15.666667% !important;
}

.product-container {
  margin-left: 15px;
}
</style>
