<template lang="html">
  <div class="nav-bar">
    <p>hello</p>
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
.nav-bar {
  height: 64px;
  background: #fff;
  position: sticky;
  top: 0;
  left: 0;
  box-shadow: 0px 3px 3px #0000001A;
  display: flex;
  justify-content: space-between;
  padding: 13px $space-m;
  font-size: 20px;
  color: $primary-color;
  z-index: 5;
}
</style>
