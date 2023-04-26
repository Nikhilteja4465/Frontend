<template>
  <MyHeader LaptopName="Nik's Computers" OwnerName="By NikhilTeja" />
  <LaptopsBox :LaptopDetails=LaptopDetails />
</template>


<script>
import MyHeader from './components/MyHeader.vue'
import LaptopsBox from './components/LaptopsBox.vue'
export default {

  name: 'App',
  components: {
    MyHeader,
    LaptopsBox
  },

  data() {
    return {
      LaptopDetails: []
    }

  },
  methods: {
    async fetchLaptops() {
      const res = await fetch("https://nikhilteja.onrender.com/api")
      const data = await res.json()

      return data
    }
  },
  async created() {
    this.LaptopDetails = await this.fetchLaptops()
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: #488286;
}

.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div {
  margin-bottom: 0.5em;

}
</style>