<template lang="html">
  <div class="carousel">
    <div class="image-conatainer">
      <img :src="carouselList[currentIndex].image" alt="">
    </div>

    <div class="carousel-dots">
      <div v-for="(slide, index) in carouselList" class="one-dot" :key="index">
        <i @click="setSlide(index)" class="fas fa-circle" :class="{'active-dot': currentIndex === index}"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      carouselList: [
        {image: 'images/pexels-alexey-demidov-9727475-min.jpg'},
        {image: 'images/pexels-irina-bekhtereva-9895110-min.jpg'},
        {image: 'images/pexels-joaquín-m-9677208-min.jpg'},
        {image: 'images/pexels-john-lee-6873095-min.jpg'},
        {image: 'images/pexels-vyacheslav-bobin-9751579-min.jpg'},
      ],
      timer: null,
      currentIndex: 0
    }
  },
  mounted() {
    this.startSlide();
  },
  methods: {
    startSlide() {
      this.timer = setInterval(this.next, 4000);
    },
    next() {
      if (this.currentIndex == this.carouselList.length - 1) {
        this.currentIndex = 0
      } else {
        this.currentIndex += 1;
      }
    },
    setSlide(n) {
      clearInterval(this.timer)
      this.currentIndex = n
      this.startSlide()
    },
  }
}
</script>

<style lang="scss" scoped>
.carousel {
}
.image-conatainer {
  width: 220px;
  height: 280px;
  border-radius: $radius-default;
  overflow: hidden;
  margin-right: $space-xxl;
  box-shadow: $box-shadow;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.carousel-dots {
  width: 220px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: $space-s;
}
.one-dot {
  padding: 0 3px;
  cursor: pointer;
  margin: 0 3px;

  i {
    font-size: 12px;
    color: white;
    border-radius: 50%;
    box-shadow: $box-shadow;
    transition: all .3s;

    &:hover {
      color: $secondary-light-700;
    }
  }
}
.active-dot {
  color: $secondary-color!important;
}
</style>
