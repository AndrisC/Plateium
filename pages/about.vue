<template>
  <div class="container">
    <div class="extended-header"></div>

    <div class="about-container">
      <div class="one-about">
        <div class="text-holder">
          <h3>The history</h3>
          <span>
            Dui vivamus arcu felis bibendum. Diam quam nulla porttitor massa id neque.
            Mauris nunc congue nisi vitae suscipit tellus mauris. Ipsum dolor sit amet
            consectetur adipiscing elit duis. Pellentesque massa placerat duis ultricies
            lacus sed. Pellentesque elit eget gravida cum. Gravida arcu ac tortor dignissim
            convallis aenean et. Vitae et leo duis ut diam. Amet est placerat in egestas.
            In massa tempor nec feugiat.
          </span>
        </div>

        <div class="image-holder">
          <img src="~/static/images/about_us_mockup.jpg" alt="">
        </div>
      </div>

      <div class="one-about">
        <div class="image-holder left-radius">
          <img src="~/static/images/pexels-alina-k-9866828-min.jpg" alt="">
        </div>

        <div class="text-holder">
          <h3>Metal posters</h3>
          <span>
            Semper viverra nam libero justo laoreet sit amet. Risus pretium quam vulputate
            dignissim suspendisse in. Venenatis lectus magna fringilla urna porttitor. Eu
            feugiat pretium nibh ipsum consequat. Gravida arcu ac tortor dignissim
            convallis aenean et. Vitae et leo duis ut diam. Amet est placerat in egestas.
            In massa tempor nec feugiat.
          </span>
        </div>
      </div>

      <div class="one-about">
        <div class="text-holder">
          <h3>Our goals</h3>
          <span>
            Dui vivamus arcu felis bibendum. Diam quam nulla porttitor massa id neque.
            Mauris nunc congue nisi vitae suscipit tellus mauris. Ipsum dolor sit amet
            consectetur adipiscing elit duis. Pellentesque massa placerat duis ultricies
            lacus sed. Pellentesque elit eget gravida cum. Gravida arcu ac tortor dignissim
            convallis aenean et. Vitae et leo duis ut diam. Amet est placerat in egestas.
            In massa tempor nec feugiat.
          </span>
        </div>

        <div class="image-holder">
          <img src="~/static/images/about_us_mockup2.jpg" alt="">
        </div>
      </div>
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
.extended-header {
  background: $primary-color;
  height: 370px;
}
.about-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: -270px;
}
.one-about {
  max-width: 700px;
  box-shadow: $box-shadow;
  border-radius: $radius-default;
  background: #fff;
  display: flex;
  margin-bottom: $space-l;
}
.text-holder {
  padding: $space-s $space-m;

  span {
    color: $font-color-light;
  }
  h3 {
    margin-bottom: $space-m;
  }
}
.image-holder {
  min-width: 250px;
  height: 320px;
  border-top-right-radius: $radius-default;
  border-bottom-right-radius: $radius-default;
  overflow: hidden;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.left-radius {
  border-top-right-radius: 0;
  border-bottom-right-radius: 0;
  border-top-left-radius: $radius-default;
  border-bottom-left-radius: $radius-default;
}
</style>
