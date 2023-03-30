<template>
  <div style="margin-top: 10px">
      <strong>{{ name }} : </strong>
      <ProductPrice :price="price"/>

      <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script setup>
import ProductPrice from "./ProductPrice.vue";
const props = defineProps({
    name: String,
    price: Number
})

const emit = defineEmits(['addToCart']);
const addToCart = () => emit('addToCart', props.name);

</script>

<style scoped>

</style>