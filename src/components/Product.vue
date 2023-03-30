<template>

</template>

<script>
export default {
    name: "Product",
    props: {
        name: String,
        price: Number
    },
    setup({name, price}) {
        console.log(name);
        console.log(price);
    }
}
</script>

<style scoped>

</style>