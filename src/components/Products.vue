<template>
  <div class="row product-container">
    <app-product></app-product>
  </div>
</template>

<script>
import Product from "./Product.vue";
export default {
  components: {
    appProduct: Product,
  },
};
</script>
