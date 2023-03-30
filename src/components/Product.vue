<template>
  <div style="margin-top: 10px">
      <strong>{{ name }} : </strong>
      <span>{{formatPrice}}</span><br>

      <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
import {computed} from "vue";

export default {
    name: "Product",
    props: {
        name: String,
        price: Number
    },
    setup(props, {attr, slots, emit}) {
        const addToCart = () => emit('addToCart', props.name);
        const formatPrice = computed(() => `$${props.price.toFixed(2)}`);

        return { addToCart, formatPrice }
    }
}
</script>

<style scoped>

</style>