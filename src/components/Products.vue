<template>
  <div class="row product-container">
    <app-product v-for="product in productList" :key="product">
      <img
        class="card-img-top"
        src="/src/assets/default.png"
        alt="Card image cap"
      />
      <div class="card-body">
        <h5 class="card-title">{{ productList.title }}</h5>
        <small> <strong>Quantity : </strong> {{ productList.quantity }} </small>
        <br />
        <small> <strong>Price : </strong> {{ productList.price }} </small>
        <br />
        <small> <strong>Total : </strong> {{ productList.totalPrice }} </small>
      </div>
    </app-product>
  </div>
</template>

<script>
import { eventBus } from "../main";
import Product from "./Product.vue";
export default {
  components: {
    appProduct: Product,
  },
  data() {
    return {
      productList: [],
    };
  },
  created() {
    eventBus.$on("productAdded", (product) => {
      this.productList.push(product);
      console.log(productList);
    });
  },
};
</script>
