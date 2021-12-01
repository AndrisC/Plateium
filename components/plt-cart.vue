<template lang="html">
  <div class="cart-container">
    <div class="title">
      <h4>Contents of your cart</h4>
    </div>

    <div class="product-container">
      <div v-for="product in products" class="one-product">
        <div class="product-image">
          <img :src="product.img" alt="">
        </div>

        <div class="information">
          <div class="order-info">
            <span class="product-name">{{product.name}}</span>
            <span class="mat-info">{{product.size}}</span>
            <span class="mat-info">{{product.material}}</span>
          </div>

          <div class="bottom-info">
            <div class="quantity-container">
              quantity: 1
            </div>

            <div class="price-container">
              <span>{{product.price}}</span>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="total-container">
      <h4>Estimated Total:</h4>

      <h4>$39.98</h4>
    </div>

    <div class="button-container">
      <plt-button @click="$router.push('/cart'), $emit('close')">To Cart</plt-button>
    </div>
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
.cart-container {
  position: absolute;
  top: 64px;
  right: $space-m;
  z-index: 100;
  box-shadow: $box-shadow;
  padding: $space-s;
  width: 330px;
  background: #fff;
  border-radius: $radius-default;
}
.product-container {
  padding-top: $space-s;
}
.one-product {
  display: flex;
  height: 124px;
  padding-bottom: $space-m;
  border-bottom: 2px dashed $border-color;
  margin-bottom: $space-m;
}
.product-image {
  width: 75px;
  height: 100px;
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
.information {
  display: flex;
  width: 210px;
  flex-direction: column;
  justify-content: space-between;
}
.product-name {
  margin-bottom: $space-xxs;
}
.order-info {
  display: flex;
  flex-direction: column;
}
.mat-info {
  font-size: $paragraph-tiny;
  color: $font-color-lighter;
}
.bottom-info {
  display: flex;
  justify-content: space-between;
}
.quantity-container {
  font-size: $paragraph-small;
}
.price-container {
  font-weight: 600;
}
.total-container {
  display: flex;
  justify-content: space-between;
}
.button-container {
  display: flex;
  justify-content: flex-end;
  margin-top: $space-m;
}
</style>
