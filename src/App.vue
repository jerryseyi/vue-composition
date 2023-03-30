<script>
  import Product from "./components/Product.vue";
  import {reactive, ref} from "vue";

  export default {
      components: {Product},
      setup() {
          const name = ref('John Doe');
          console.log(name, name.value, 'from setup');
          const product = reactive({name: 'Laptop', price: 1300})
          const greeting = () => alert('welcome ' + name);
          const addItemToCart = (item) => alert(`one ${item} added to cart`);

          return {name, greeting, addItemToCart, product };
      },

      created() {
          console.log(this.name, 'created hook');
      }
  }
</script>

<template>
  <div>
<!--      no need to use .value in the template-->
      <input type="text" v-model="name"><h3>{{ name }}</h3>
      <button @click="greeting">Greetings</button>
      <br>
      <Product :name="product.name" :price="product.price" @addToCart="addItemToCart"/>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
