<template>
  <div class="container">
    <div class="header-container">
      <div class="image-carousel">
        <plt-carousel/>
      </div>

      <div class="information-container">
        <h2 class="welcome">Welcome to Plateium</h2>

        <h1>Find the best photos or designs for your house.</h1>

        <div class="button-container">
          <plt-button @click="$router.push('/collection')">Explore collection</plt-button>
        </div>
      </div>
    </div>

    <div class="categories-container">
      <div class="section-title">
        <h4>Categories</h4>
      </div>

      <div class="categories">
        <div @click="$router.push('/collection')" class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-alexey-demidov-9727475-min.jpg" alt="">
          </div>

          <span class="category-name">Nature</span>
        </div>

        <div @click="$router.push('/collection')" class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-anna-kozlova-10162708-min.jpg" alt="">
          </div>

          <span class="category-name">City</span>
        </div>

        <div @click="$router.push('/collection')" class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-guryan-9579125-min.jpg" alt="">
          </div>

          <span class="category-name">Animals</span>
        </div>

        <div @click="$router.push('/collection')" class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-eb-er-9049274-min.jpg" alt="">
          </div>

          <span class="category-name">Cars</span>
        </div>

        <div @click="$router.push('/collection')" class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-thais-cordeiro-3873664-min.jpg" alt="">
          </div>

          <span class="category-name">Buildings</span>
        </div>

        <div @click="$router.push('/collection')" class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-skyler-sion-9808227-min.jpg" alt="">
          </div>

          <span class="category-name">Sea</span>
        </div>

        <div @click="$router.push('/collection')" class="one-category last-category">
          <div class="category-image">
            <img src="~/static/images/pexels-denis-trushtin-9855417-min.jpg" alt="">
          </div>

          <span class="category-name">People</span>
        </div>
      </div>
    </div>

    <div class="middle-information-container">
      <div class="middle-image-container">
        <img src="~/static/images/poster_mockup.png" alt="">
      </div>

      <div class="middle-text">
        <h1 class="middle-text-title">Your wall, your choice</h1>
        <h1>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</h1>
      </div>
    </div>

    <div class="ratings-container">
      <plt-rating v-for="rating in ratings" :rating="rating"/>
    </div>

    <div class="newsletter-container">
      <h2>Join our newsletter!</h2>

      <div class="email-container">
        <plt-input placeholder="Email" class="email-input" title="Your email address"/>

        <plt-button>Subscribe</plt-button>
      </div>

      <plt-checkbox label="Yes, I would like to recieve email with newsletters"/>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ratings: [
        {
          img: 'images/pexels-zhuravleva-anastasia-9985770-min.jpg',
          name: 'Ocean waves',
          rating: 4,
          customer: 'Jozefo Reut',
          comment: 'Ut aliquam purus sit amet luctus magna. In hac ',
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
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.header-container {
  background: $primary-color;
  height: 370px;
  width: 100%;
  display: flex;
  padding: $space-m;
  justify-content: center;
}
.categories-container {
  padding: $space-l;
  max-width: 1010px;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
}
.categories {
  display: flex;
}
.section-title {
  margin-bottom: $space-s;
}
.one-category {
  margin-right: $space-m;
  display: flex;
  flex-direction: column;
  align-items: center;
  cursor: pointer;

}
.last-category {
  margin-right: 0;
}
.category-image {
  width: 110px;
  height: 140px;
  border-radius: $radius-default;
  overflow: hidden;
  box-shadow: $box-shadow;
  transition: all .2s;
  &:hover {
    transform: scale(1.02);
    box-shadow: 0px 6px 12px 2px rgba(28, 38, 42, 0.45);
  }

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.information-container {
  text-align: right;
  width: 450px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-bottom: $space-m;
}
.category-name {
  margin-top: $space-xs;
}
.middle-information-container {
  border-top: 1px solid $border-color;
  border-bottom: 1px solid $border-color;
  padding: $space-l $space-m;
  display: flex;
  justify-content: center;
  max-width: 1000px;
  margin: 0 auto;
}
.middle-image-container {
  width: 500px;
  height: 600px;
  border-radius: $radius-default;
  overflow: hidden;
  margin-right: $space-l;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.middle-text {
  width: 50%;
}
.middle-text-title {
  margin-bottom: $space-l;
}
.newsletter-container {
  border-radius: $radius-default;
  box-shadow: $box-shadow;
  padding: $space-l;
  width: 80%;
  max-width: 1000px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: $space-l auto;

  h2 {
    margin-bottom: $space-s;
  }
}
.ratings-container {
  max-width: 1000px;
  display: flex;
  grid-gap: $space-m;
  padding: $space-l 0 $space-xl 0;
  border-bottom: 1px solid $border-color;
}
.email-container {
  display: flex;
  align-items: flex-end;

  .email-input {
    margin-right: $space-m;
  }
}
</style>
