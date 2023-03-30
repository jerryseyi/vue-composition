<template>
  <span>{{formatPrice}}</span>
</template>

<script>
import {computed} from "vue";
import {inject} from "vue";

export default {
    name: "ProductPrice",
    props: ['price'],
    setup(props) {
        const currency = inject("currency", "$");
        const formatPrice = computed(() => `${currency} ${props.price.toFixed(2)}`);

        return { formatPrice }
    }
}
</script>

<style scoped>

</style>