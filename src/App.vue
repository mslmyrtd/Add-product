<template>
  <div class="container">
    <h1 class="text-center">Add Product App</h1>
    <hr />
    <new-product></new-product>
    <br /><br />
    <div class="progress">
      <div
        class="progress-bar bg-info"
        role="progressbar"
        style="width: 0%"
        aria-valuenow="50"
        aria-valuemin="0"
        aria-valuemax="100"
      >
        0/10
      </div>
    </div>
    <br /><br />
    <h3 class="text-center">Added Product List</h3>
    <hr />
    <div class="row product-container">
      <div class="col-md-2 card">
        <img
          class="card-img-top"
          src="/src/assets/default.png"
          alt="Card image cap"
        />
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <small> <strong>Adet : </strong> 1 </small>
          <br />
          <small> <strong>Fiyat : </strong> 10 </small>
          <br />
          <small> <strong>Tutar : </strong> 10 </small>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NewProduct from "../src/components/NewProduct.vue";
export default {
  components: {
    NewProduct,
  },
  data() {
    return {
      imageList: [],
      product: {
        selectedImage: null,
      },
    };
  },
  methods: {
    onChange(e) {
      const file = e.target.files[0];
      this.product.selectedImage = URL.createObjectURL(file);
    },
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
