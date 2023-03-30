<template>

</template>

<script>
export default {
    name: "Product",
    props: {
        name: String,
        price: Number
    },
    setup(props, context) {
        console.log(props.name);
        console.log(props.price);
    }
}
</script>

<style scoped>

</style>