<template>
    <div>
        <h1>{{ LaptopName }}</h1>
        <h4>{{ OwnerName }}</h4>
    </div>
</template>
<script>
export default {
    name: "MyHeader",
    props: {
        LaptopName: String,
        OwnerName: String
    }
}
</script>
<style scoped>
div {
    text-align: center;
    background-color: #E1F4CB;

    padding: 5px;
}
</style>