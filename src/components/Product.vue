<template>
  <div style="margin-top: 10px">
      <strong>{{ name }} : </strong>
      <ProductPrice :price="price"/>

      <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
import ProductPrice from "./ProductPrice.vue";

export default {
    name: "Product",
    components: {ProductPrice},
    props: {
        name: String,
        price: Number
    },
    setup(props, {attr, slots, emit}) {
        const addToCart = () => emit('addToCart', props.name);

        return { addToCart }
    },

}
</script>

<style scoped>

</style>