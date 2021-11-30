<template lang="html">
  <div class="container">

  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          _id: '9727475',
          name: 'Misty day',
          img: 'images/pexels-simon-berger-10057659-min.jpg',
          price: '$19.99',
          size: 'Size XL',
          quantity: 1,
          material: 'Aluminium',
        },
        {
          _id: '10162708',
          name: 'City from below',
          img: 'images/pexels-anna-kozlova-10162708-min.jpg',
          price: '$19.99',
          size: 'Size XL',
          quantity: 1,
          material: 'Aluminium',
        },
      ]
    }
  },
  mounted() {
    if(!process.client) return;
    let savedData = localStorage.getItem("cartItem")
  }
}
</script>

<style lang="scss" scoped>

</style>
