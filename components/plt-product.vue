<template>
  <div class="container">
    <div class="image-container">
      <img :src="product.img" alt="">
    </div>

    <div class="description-container">
      <p class="product-name">{{product.name}}</p>
      <p class="artist">By {{product.artist}}</p>
    </div>

    <div class="button-container">
      <plt-button @click="$router.push({name: 'product', params: {product: product}})" class="plt-button" type="outlined">Details/Buy</plt-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      default: () => {}
    },
  },
}
</script>

<style lang="scss" scoped>
.container {
  padding: 0!important;
  display: flex;
  flex-direction: column;
  width: 100%!important;
}
.image-container {
  width: 100%;
  height: 300px;
  border-radius: $radius-default;
  overflow: hidden;
  margin-bottom: $space-xs;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.description-container {
  width: 100%;
  margin-bottom: $space-s;
}
.button-container {
  width: 100%;
}
.product-name {
  font-weight: 500;
  margin-bottom: $space-xxs;
}
.artist {
  color: $font-color-lighter;
  font-size: $paragraph-tiny;
}
.plt-button {
  width: 100%;
}
</style>
