<template>
  <div class="container">
    <div class="header-container">
      <div class="image-carousel">
        <img src="~/static/images/pexels-alexey-demidov-9727475-min.jpg" alt="">
      </div>
      <div class="information-container">
        <h2 class="welcome">Welcome to Plateium</h2>
        <h1>Find the best photos or designs for your house.</h1>
      </div>
    </div>

    <div class="categories-container">
      <div class="section-title">
        <h4>Categories</h4>
      </div>

      <div class="categories">
        <div class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-alexey-demidov-9727475-min.jpg" alt="">
          </div>

          <span class="category-name">Nature</span>
        </div>

        <div class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-anna-kozlova-10162708-min.jpg" alt="">
          </div>

          <span class="category-name">City</span>
        </div>

        <div class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-guryan-9579125-min.jpg" alt="">
          </div>

          <span class="category-name">Animals</span>
        </div>

        <div class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-евгения-егорова-9049274-min.jpg" alt="">
          </div>

          <span class="category-name">Cars</span>
        </div>

        <div class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-thais-cordeiro-3873664-min.jpg" alt="">
          </div>

          <span class="category-name">Buildings</span>
        </div>

        <div class="one-category">
          <div class="category-image">
            <img src="~/static/images/pexels-skyler-sion-9808227-min.jpg" alt="">
          </div>

          <span class="category-name">Sea</span>
        </div>

        <div class="one-category last-category">
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
        <h1>Your wall, your choice</h1>
        <h1>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</h1>
      </div>
    </div>

    <div class="ratings-container">

    </div>

    <div class="newsletter-container">
      <h1>Join our newsletter!</h1>

      <div class="email-container">

      </div>

      <!-- ide checkbox -->
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {

    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  height: 100%;
  box-sizing: border-box;
}
.header-container {
  background: $primary-color;
  height: 370px;
  display: flex;
  // align-items: center;
  padding: $space-m;
  justify-content: center;
}
.image-carousel {
  width: 220px;
  height: 280px;
  border-radius: $radius-default;
  overflow: hidden;
  margin-right: $space-xxl;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
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

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.welcome {
  margin-bottom: $space-l;
}
.information-container {
  text-align: right;
  width: 450px;
}
.category-name {
  margin-top: $space-xs;
}
.middle-information-container {
  border-top: 2px solid $color-gray-light;
  border-bottom: 2px solid $color-gray-light;
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
.newsletter-container {
  border-radius: $radius-default;
  height: 250px;
  box-shadow: $box-shadow;
  padding: $space-l;
  max-width: 90%;
  max-width: 950px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: $space-l auto;
}
</style>
