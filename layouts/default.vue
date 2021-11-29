<template>
  <div>

    <NavBar></NavBar>

    <div class="default-layout">
      <div class="content" id="content">
        <Nuxt />
      </div>
    </div>

  </div>
</template>

<script>
import NavBar from '~/components/NavBar'

export default {
  data() {
    return {
    }
  },
  components: {
    NavBar
  }
}
</script>

<style lang="scss">
html {
  font-family: Inter;
  font-size: 18px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
.content {
  width: 100%;
  overflow-y: auto;
  border-radius: 10px 0 0 10px;
  background: #fff;
}
.default-layout {
  height: calc(100vh - 64px);
  width: 100%;
  display: flex;
  background: #fff;
}

</style>
