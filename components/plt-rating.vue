<template lang="html">
  <div class="rating-container">
    <div class="image-container">
      <img :src="rating.img" alt="">
    </div>

    <div class="info-container">
      <div class="product-name">
        <span>{{rating.name}}</span>
      </div>

      <div class="rating">
        <i v-for="i in 5" class="far fa-star"></i>
      </div>

      <div class="review">
        <span class="customer">{{rating.customer}}</span>
        <span class="comment">- {{rating.comment}}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    rating: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style lang="scss" scoped>
.rating-container {
  min-width: 250px;
  max-width: 380px;
  border-radius: $radius-default;
  box-shadow: $box-shadow;
  padding: $space-xs;
  display: flex;
  flex-direction: row;
}
.image-container {
  width: 20%;
  min-width: 50px;
  max-width: 80px;
  height: 90px;
  overflow: hidden;
  border-radius: $radius-small;
  margin-right: $space-xs;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.info-container {
  display: flex;
  flex-direction: column;
  width: 80%;
}
.rating {
  display: flex;
  margin: $space-xxs 0 $space-xs 0;

  i {
    color: $secondary-color;
    font-size: 11px;
    margin-right: $space-xxs;
  }
}
.product-name {
  font-size: $paragraph-small;
  font-weight: 500;
}
.review {
  font-size: $paragraph-tiny;
}
.comment {
  color: $font-color-lighter;
}
</style>
