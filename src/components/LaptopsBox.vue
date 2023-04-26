<template>
    <div v-for="Laptop of LaptopDetails" :key="Laptop.productName">
        <LaptopSingle :Laptop="Laptop" />

    </div>
</template>
<script>
import LaptopSingle from './LaptopSingle.vue';
export default {
    name: "LaptopsBox",
    props: {
        LaptopDetails: Array
    },
    components: {
        LaptopSingle
    }
}
</script>
<style></style>