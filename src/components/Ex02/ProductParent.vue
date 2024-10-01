<template>
  <div>
    <h1>Ex02</h1>
    <product-children
      :id="id"
      :name="productName"
      :price="price"
      :quantity="quantity"
    ></product-children>
  </div>
</template>

<script setup>
import ProductChildren from "./ProductChildren.vue";
import { ref } from "vue";
const id = ref(1);
const productName = ref("Buoi Ba Roi");
const price = ref("12.000đ");
const quantity = ref(10);
</script>

<style></style>