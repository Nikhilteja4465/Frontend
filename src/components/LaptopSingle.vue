<template>
    <div class="grid-container">
        <swiper :options="swiperOptions">
            <swiper-slide v-for="(Laptop, index) in Laptop" :key="Laptop.serialNo">
                <div :class="{ 'grid-item': true, 'odd': index % 2 === 0, 'even': index % 2 !== 0 }">
                    <h2 class="product-name">Product Name: {{ Laptop.productName }}</h2>
                    <h4>Serial Number: {{ Laptop.serialNo }}</h4>
                    <h4>Price of Laptop: {{ Laptop.price }}</h4>
                    <a :href="Laptop.URL" target="_blank">Click here for Product Details</a>
                    <h4>Released Date: {{ Laptop.ReleaseDate }}</h4>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'

export default {
    components: {
        Swiper,
        SwiperSlide
    },
    props: {
        Laptop: Array
    },
    data() {
        return {
            swiperOptions: {
                autoplay: true,
                loop: true
            }
        }
    }
}
</script>
  
<style scoped>
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-gap: 1em;
}

.grid-item {
    color: black;
    padding: 1em;
    text-align: center;
    aspect-ratio: 6 / 1;
    border: 1px solid black;
    border-radius: 10px;
}

.product-name {
    font-size: 24px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 10px;
}

.odd {
    background-color: #DCD6F7 !important;
}

.even {
    background-color: #297373;
}

a {
    text-decoration: none;
    color: black;
}

a:hover {
    background-color: #FFE5D4;
}
</style>







