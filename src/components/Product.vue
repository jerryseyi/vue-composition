<template>
  <div style="margin-top: 10px">
      <strong>{{ name }} : </strong>
      <span>{{formatPrice}}</span><br>

      <button @click="addToCart">Add to Cart</button>
  </div>
</template>

<script>
export default {
    name: "Product",
    props: {
        name: String,
        price: Number
    },
    setup(props, {attr, slots, emit}) {
        const addToCart = () => emit('addToCart', props.name);

        return { addToCart }
    },
    computed: {
        formatPrice() {
            return `$${this.price.toFixed(2)}`;
        }
    }
}
</script>

<style scoped>

</style>