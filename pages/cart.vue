<template lang="html">
  <div class="container">
    <div class="extended-header"></div>

    <div class="product-container">
      <div class="title">
        <h4>Your cart</h4>
      </div>

      <div v-for="(product, index) in products" :key="product._id" class="one-product">
        <div class="big-image">
          <img :src="product.img" alt="">
        </div>

        <div class="details-wrapper">
          <div class="">
            <div class="info">
              <h2>{{product.name}}</h2>
            </div>

            <div class="field-wrapper">
              <plt-select
              :show-labels="false"
              :options="sizeOptions"
              track-by="id"
              v-model="selectedSize[index]"
              label="name"
              title="Select Size"
              placeholder="Size"
              class="plt-select"
              />

              <plt-select
              :show-labels="false"
              :options="matOptions"
              track-by="id"
              v-model="selectedMaterial[index]"
              label="name"
              title="Select material"
              placeholder="material"
              class="plt-select"
              />
            </div>

            <div class="quantity-wrapper">
              <button @click="decQuantity(product)" class="negative quantity-button left" type="button" name="button">
                <i class="fas fa-minus"></i>
              </button>

              <div class="quantity">
                <span>{{product.quantity}}</span>
              </div>

              <button @click="product.quantity = product.quantity + 1" class="positive quantity-button right" type="button" name="button">
                <i class="fas fa-plus"></i>
              </button>
            </div>
          </div>

          <div class="bottom-info">
            <div class="price">
              <h4 class="price-text">Price:</h4>
              <h4>{{product.price}}</h4>
            </div>
          </div>
        </div>
      </div>

      <div class="total-container">
        <h3 class="total-text">Estimated Total:</h3>
        <div class="line"></div>
        <h3>$39.98</h3>
      </div>

      <div class="button-container">
        <plt-button @click="$router.push('/collection')" type="outlined">Continue shopping</plt-button>
        <plt-button @click="$router.push('/checkout')">To checkout</plt-button>
      </div>
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
      ],
      sizeOptions: [
        {name: 'M - 60cm x 30cm', id: 0},
        {name: 'L - 90cm x 45cm', id: 1},
        {name: 'XL - 120cm x 60cm', id: 2},
      ],
      matOptions: [
        {name: 'Aluminium', id: 0},
        {name: 'Stainless steel', id: 1},
      ],
      selectedSize: [
        {name: 'XL - 120cm x 60cm', id: 0},
        {name: 'XL - 120cm x 60cm', id: 1},
      ],
      selectedMaterial: [
        {name: 'Aluminium', id: 0},
        {name: 'Aluminium', id: 1},
      ],
    }
  },
  mounted() {
    if(!process.client) return;
    let savedData = localStorage.getItem("cartItem")
  },
  methods: {
    decQuantity(prod) {
      if (prod.quantity > 1) {
        prod.quantity = prod.quantity - 1
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.extended-header {
  background: $primary-color;
  height: 370px;
  width: 100%;
}
.product-container {
  background: #fff;
  border-radius: $radius-default;
  box-shadow: $box-shadow;
  padding: $space-m;
  margin-top: -300px;
  margin-bottom: 100px;
}
.title {
  margin-bottom: $space-s;
}
.one-product {
  max-width: 650px;
  display: flex;
  padding-bottom: $space-m;
  margin: $space-s 0 $space-m 0;
  border-bottom: 2px solid $border-color;
}
.big-image {
  width: 235px;
  height: 310px;
  border-radius: $radius-small;
  overflow: hidden;
  margin: 0 $space-m 0 0;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.details-wrapper {
  width: 400px;
  height: 310px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.info {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: $space-xs;
}
.artist {
  color: $font-color-light;
  margin-bottom: $space-s;
}
.stars {
  i {
    margin-left: $space-xs;
    color: $secondary-color;
    font-size: 22px;
  }
}
.field-wrapper {
  width: 260px;
}
.bottom-info {
  display: flex;
  justify-content: flex-end;
}
.price {
  display: flex;
}
.price-text {
  color: $font-color-lighter;
  margin-right: $space-xs;
}
.total-container {
  display: flex;
  justify-content: space-between;
  margin-bottom: $space-l;
}
.total-text {
  color: $font-color-lighter;
}
.line {
  display: flex;
  width: 50%;
  border-bottom: 2px dashed $border-color;
}
.button-container {
  display: flex;
  justify-content: flex-end;
  grid-gap: $space-m;
}
.quantity-wrapper {
  display: flex;
  margin-top: $space-m;
  align-items: center;
}
.quantity-button {
  border: 2px solid $border-color;
  color: $font-color-lighter;
  cursor: pointer;
  background: #fff;
  height: 40px;
  outline: none;
  width: 38px;
  transition: all .3s ease;

  &:hover {
    border-color: $font-color-lighter;
    color: $font-color-light;
  }
}
.left {
  border-top-left-radius: $radius-default;
  border-bottom-left-radius: $radius-default;
}
.right {
  border-top-right-radius: $radius-default;
  border-bottom-right-radius: $radius-default;
}
.quantity {
  width: 38px;
  height: 40px;
  border-top: 2px solid $border-color;
  border-bottom: 2px solid $border-color;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
