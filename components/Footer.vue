<template lang="html">
  <div class="footer">
    <div class="shop-container">
      <div class="footer-title">
        <span>Shop</span>
      </div>

      <div @click="$router.push('/collection')" class="menu-item">
        <span>Collection</span>
      </div>
      <div @click="$router.push('/about')" class="menu-item">
        <span>About us</span>
      </div>
      <div @click="$router.push('/')" class="menu-item">
        <span>Terms of use</span>
      </div>
      <div @click="$router.push('/')" class="menu-item">
        <span>Privacy policy</span>
      </div>
    </div>

    <div class="shop-container">
      <div class="footer-title">
        <span>References</span>
      </div>

      <div @click="$router.push('/')" class="menu-item">
        <span>Artists</span>
      </div>
      <div @click="$router.push('/')" class="menu-item">
        <span>Source of images</span>
      </div>
    </div>

    <div class="shop-container">
      <div class="footer-title">
        <span>Contacts</span>
      </div>

      <div class="menu-item">
        <span>Email address - plateium@email.com</span>
      </div>
      <div class="menu-item">
        <span>Phone - +123 234 2344</span>
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
.footer {
  min-height: 230px;
  width: 100%;
  display: flex;
  justify-content: center;
  padding: $space-xs;
  background: $primary-color;
  color: $font-color;
}
.shop-container {
  padding: $space-m $space-xl;
}
.footer-title {
  margin-bottom: $space-s;
}
.menu-item {
  color: $font-color-light;
  margin-bottom: $space-xs;
  cursor: pointer;
}
</style>
