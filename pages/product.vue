<template lang="html">
  <div class="container">
    <div class="product-container">
      <div class="images-wrapper">
        <div class="small-images-wrapper">
          <div v-for="i in 2" class="small-image">
            <img :src="$route.params.product.img" alt="">
          </div>
        </div>

        <div class="big-image">
          <img :src="$route.params.product.img" alt="">
        </div>
      </div>

      <div class="details-wrapper">
        <div class="">
          <div class="info">
            <h2>{{$route.params.product.name}}</h2>

            <div class="stars">
              <i v-for="i in 5" class="far fa-star"></i>
            </div>
          </div>

          <div class="artist">
            <span>{{$route.params.product.artist}}</span>
          </div>

          <div class="field-wrapper">
            <plt-select
            :show-labels="false"
            :options="sizeOptions"
            track-by="id"
            v-model="selectedSize"
            label="name"
            title="Select Size"
            placeholder="Size"
            class="plt-select"
            />

            <plt-select
            :show-labels="false"
            :options="matOptions"
            track-by="id"
            v-model="selectedMaterial"
            label="name"
            title="Select material"
            placeholder="material"
            class="plt-select"
            />
          </div>

          <div class="stock-wrapper">
            <span v-if="$route.params.product.stock == 0" class="out-of-stock">Out of stock</span>
            <span v-else>On Stock!</span>
          </div>

          <div class="quantity-wrapper">
            <button @click="decQuantity()" class="negative quantity-button left" type="button" name="button">
              <i class="fas fa-minus"></i>
            </button>

            <div class="quantity">
              <span>{{quantity}}</span>
            </div>

            <button @click="quantity = quantity + 1" class="positive quantity-button right" type="button" name="button">
              <i class="fas fa-plus"></i>
            </button>
          </div>
        </div>

        <div class="bottom-info">
          <div class="price">
            <h1>{{$route.params.product.price}}</h1>
          </div>

          <div class="button-container">
            <plt-button @click="addToCart($route.params.product)">Add to cart</plt-button>
          </div>
        </div>
      </div>
    </div>

    <div class="simmilar-container">
      <div class="title">
        <h3>Simmilar products</h3>
      </div>

      <div class="products">
        <plt-product v-for="product in products" :key="product._id" :product="product"/>
      </div>
    </div>

    <div class="ratings-container">
      <plt-rating v-for="rating in ratings" :key="rating.name" :rating="rating"/>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          _id: '9654126',
          name: 'Forest birdview',
          artist: 'Yaroslav Chaadaev',
          img: 'images/pexels-yaroslav-chaadaev-9654126-min.jpg',
          price: '$19.99',
          rating: 4,
          stock: 2,
        },
        {
          _id: '9038269',
          name: 'Open window',
          artist: 'Yew Hui Tan',
          img: 'images/pexels-yew-hui-tan-9038269-min.jpg',
          price: '$19.99',
          rating: 4,
          stock: 2,
        },
        {
          _id: '9038606',
          name: 'Pink house',
          artist: 'Yew Hui Tan',
          img: 'images/pexels-yew-hui-tan-9038606-min.jpg',
          price: '$19.99',
          rating: 4,
          stock: 2,
        },
        {
          _id: '9985770',
          name: 'Ocean waves',
          artist: 'Zhuravleva Anastasia',
          img: 'images/pexels-zhuravleva-anastasia-9985770-min.jpg',
          price: '$19.99',
          rating: 4,
          stock: 2,
        },
        {
          _id: '9733511',
          name: 'Look up',
          artist: 'Aртём H',
          img: 'images/pexels-артём-н-9733511-min.jpg',
          price: '$19.99',
          rating: 4,
          stock: 2,
        },
      ],
      ratings: [
        {
          img: 'images/pexels-zhuravleva-anastasia-9985770-min.jpg',
          name: 'Ocean waves',
          rating: 4,
          customer: 'Jozefo Reut',
          comment: 'Ut aliquam purus sit amet luctus venenatis lectus magna. In hac ',
        },
        {
          img: 'images/pexels-skyler-sion-9881700-min.jpg',
          name: 'Sailing',
          rating: 4,
          customer: 'Saeed Jonatan',
          comment: 'Sapien eget mi proin sed. Pharetra sit amet aliquam.',
        },
        {
          img: 'images/pexels-kira-schwarz-10157052-min.jpg',
          name: 'Fly',
          rating: 4,
          customer: 'JUzziel Irvin',
          comment: 'Odio pellentesque diam volutpat commodo.',
        }
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
      selectedSize: {},
      selectedMaterial: {},
      quantity: 1
    }
  },
  methods: {
    addToCart(product) {
      localStorage.setItem('cartItem' ,this.$route.params.product.img)
    },
    decQuantity() {
      if (this.quantity > 1) {
        this.quantity = this.quantity - 1
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
.product-container {
  max-width: 1300px;
  display: flex;
  margin: $space-xl 0;
}
.images-wrapper {
  display: flex;
}
.small-image {
  width: 125px;
  height: 155px;
  overflow: hidden;
  border-radius: $radius-small;
  margin-bottom: $space-m;
  cursor: pointer;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.big-image {
  width: 430px;
  height: 476px;
  border-radius: $radius-small;
  overflow: hidden;
  margin: 0 $space-l 0 $space-m;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.details-wrapper {
  width: 400px;
  height: 476px;
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
  justify-content: space-between;
}
.simmilar-container {
  padding: $space-l 0;
  border-top: 2px solid $border-color;
  border-bottom: 2px solid $border-color;
}
.title {
  margin-bottom: $space-m;
}
.products {
  display: flex;
  grid-gap: $space-m;
}
.ratings-container {
  max-width: 1075px;
  display: flex;
  grid-gap: $space-m;
  padding: $space-l 0 $space-xl 0;
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
