<template>
  <div class="row">
    <div class="card offset-2 col-md-3">
      <div class="card-body tex-center d-flex align-items-center flex-column">
        <img
          height="128"
          class="img-responsive text-center mb-3"
          :src="
            product.selectedImage == null
              ? '/src/assets/default.png'
              : product.selectedImage
          "
        />
        <input
          ref="file"
          type="file"
          style="display: none;"
          @change="onChange($event)"
          class="form-control"
        />
        <button
          class="btn btn-outline-secondary "
          type="button"
          @click="$refs.file.click()"
        >
          Select Picture
        </button>
      </div>
    </div>
    <div class="col-md-5">
      <div class="col-md-11 card">
        <div class="card-body">
          <div class="form-group">
            <label>Product Name</label>
            <input
              v-model="product.title"
              type="text"
              class="form-control"
              placeholder="enter product name"
            />
          </div>
          <div class="row">
            <div class="form-group col-md-6">
              <label>Product Quantity</label>
              <input
                v-model="product.quantity"
                type="text"
                class="form-control"
                placeholder=" product quantity"
              />
            </div>
            <div class="form-group col-md-6">
              <label>Product Price</label>
              <input
                v-model="product.price"
                type="text"
                class="form-control"
                placeholder="enter price"
              />
            </div>
          </div>
          <button @click="addProduct" class="btn btn-outline-info btn-block">
            Add!
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { eventBus } from "../main";
export default {
  data() {
    return {
      product: {
        title: null,
        quantity: null,
        price: null,
        selectedImage: null,
        totalPrice: null,
      },
    };
  },
  methods: {
    onChange(e) {
      const file = e.target.files[0];
      this.product.selectedImage = URL.createObjectURL(file);
    },
    addProduct() {
      this.product.totalPrice = this.product.quantity * this.product.price;
      eventBus.$emit("productAdded", this.product);
      this.product = {
        title: null,
        quantity: null,
        price: null,
        selectedImage: null,
        totalPrice: null,
      };
    },
  },
};
</script>
