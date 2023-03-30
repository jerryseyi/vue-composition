<script>
  import Product from "./components/Product.vue";

  export default {
      components: {Product},
      setup() {
          const name = 'John Doe';

          const greeting = () => {
              alert('welcome ' + name);
          }
          return {name, greeting };
      }
  }
</script>

<template>
  <div>
      <h3>{{ name }}</h3>
      <button @click="greeting">Greetings</button>
      <Product name="Laptop" :price="1300"/>
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
