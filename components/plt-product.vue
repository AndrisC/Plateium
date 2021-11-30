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
  data: () =>  ({

  })
}
</script>

<style lang="scss" scoped>

</style>
