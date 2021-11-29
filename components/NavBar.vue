<template lang="html">
  <div class="nav-bar">
    <div @click="$router.push('/')" class="logo-container">
      <h2>Plateium</h2>
    </div>

    <div class="navigation-container">
      <div @click="$router.push('/collection')" class="menu-item">
        <span>Collection</span>
      </div>
      <div @click="$router.push('/about')" class="menu-item">
        <span>About</span>
      </div>
      <div @click="$router.push('/contacts')" class="menu-item border-right">
        <span>Contact</span>
      </div>
      <div @click="$router.push('/login')" class="menu-item">
        <span>Sign in</span>
      </div>
      <div class="menu-item">
        <span>Cart</span>
        <span>(0)</span>
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
.nav-bar {
  height: 64px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: $space-xs;
  background: $primary-color;
  color: $font-color;
}
.navigation-container {
  display: flex;
}
.logo-container {
  cursor: pointer;
  margin: auto 0;
}
.menu-item {
  display: flex;
  align-items: center;
  font-weight: 500;
  margin: 0 $space-s;
  cursor: pointer;
}
.border-right {
  padding: 0 $space-m 0 0;
  border-right: 2px solid $font-color;
}

</style>
