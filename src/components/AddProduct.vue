<template>
  <div>
    <button @click="openModal" class="add-button">Add Product</button>
    <div class="modal" :class="{ 'modal-open': isModalOpen }">
      <div class="modal-content">
        <span @click="closeModal" class="close-button">×</span>
        <h2>Add New Product</h2>
        <form @submit.prevent="addProduct">
          <div class="name">
            <label for="productName">Product Name</label><br />
            <input
              type="text"
              id="productName"
              v-model="newProduct.ProdName"
              required
            />
          </div>
          <div class="product-url">
            <label for="productUrl">Product URL</label><br />
            <input
              type="url"
              id="productUrl"
              v-model="newProduct.ProdUrl"
              required
            />
          </div>
          <div class="quantity">
            <label for="quantity">Quantity</label><br />
            <input
              type="number"
              id="quantity"
              v-model.number="newProduct.quantity"
              required
            />
          </div>
          <div class="amount">
            <label for="amount">Amount</label><br />
            <input
              type="number"
              id="amount"
              v-model.number="newProduct.Price"
              required
            />
          </div>
          <div class="Brand">
            <label for="Brand">Brand</label><br />
            <input
              type="text"
              id="Brand"
              v-model.number="newProduct.Brand"
              required
            />
          </div>
          <div class="category">
            <label for="category">Category</label><br />
            <input
              type="text"
              id="category"
              v-model="newProduct.category"
              required
            />
          </div>

          <button type="submit" class="submit">Add</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      isModalOpen: false,
      newProduct: {
        ProdName: "",
        ProdUrl: "",
        quantity: 0,
        Price: 0,
        Brand: "",
        category: "",
      },
    };
  },
  methods: {
    async addProduct() {
      try {
        const response = await axios.post(
          "https://watchtime.onrender.com/product",
          this.newProduct
        );
        const addedProduct = response.data;
        this.newProduct = {
          ProdName: "",
          ProdUrl: "",
          quantity: 0,
          Price: 0,
          Brand: "",
          category: "",
        };

        this.closeModal();
      } catch (error) {
        console.error("Error adding product:", error);
      }
    },
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Julius+Sans+One&family=Monoton&display=swap");

.add-button {
  width: 5rem;
  background-color: black;
  color: white;
  height: 3rem;
  font-family: "Julius Sans One", sans-serif;
  margin-top: 1rem;
  margin-right: 50rem;
}

.add-button:hover {
  transition: 0.5s;
  background-color: white;
  box-shadow: 0 0 10px white;
  color: black;
}

h2 {
  font-family: "Julius Sans One", sans-serif;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  overflow: auto;
}

.modal-content {
  background-color: black;
  color: white;
  margin: 3.5% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
  height: 40rem;
  text-align: center;
  display: flex;
  flex-direction: column;
}

.name {
  margin: 1rem;
}

.quantity {
  margin: 1rem;
}

.Brand {
  margin: 1rem;
}

.product-url {
  margin: 1rem;
}

.amount {
  margin: 1rem;
}

.category {
  margin: 1rem;
}

.close-button {
  color: white;
  float: right;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
}

.close-button:hover,
.close-button:focus {
  color: white;
  text-decoration: none;
  cursor: pointer;
}

.modal-open {
  display: block;
}

input {
  border: none;
  background: transparent;
  border-bottom: 2px solid white;
  height: 2rem;
  color: white;
}

.submit {
  background-color: black;
  color: white;
  font-family: "Julius Sans One", sans-serif;
  width: 5rem;
  height: 3rem;
}

.submit:hover {
  transition: 0.5s;
  background-color: white;
  box-shadow: 0 0 10px white;
  color: black;
}
</style>
