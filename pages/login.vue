<template>
  <div class="container">
    <div class="login-wrapper">
      <div class="image-container">
        <img src="~/static/images/termek-mockup-login.jpg" alt="">
      </div>

      <div class="login-container">
        <div class="title">
          <h3>Login</h3>
        </div>

        <div class="input-container">
          <plt-input title="E-mail address"/>
          <plt-input title="Password"/>
        </div>

        <div class="checkbox-container">
          <plt-checkbox label="Remember me"/>
        </div>

        <div class="button-container">
          <plt-button @click="$router.push('/')" class="plt-button">Login</plt-button>

          <p>Don't have an account?</p>
          <plt-button @click="$router.push('/registration')" class="plt-button" type="outlined">Registration</plt-button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'login',
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.login-wrapper {
  display: flex;
  box-shadow: $box-shadow;
  border-radius: $radius-default;
}
.image-container {
  width: 290px;
  border-top-left-radius: $radius-default;
  border-bottom-left-radius: $radius-default;
  overflow: hidden;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.login-container {
  padding: $space-m;
}
.title {
  margin-bottom: $space-m;
}
.button-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: $space-l;

  p {
    margin: $space-s 0 $space-xs 0;
    font-size: 14px;
    color: $font-color-lighter;
  }
}
.plt-button {
  width: 200px;
}
</style>
