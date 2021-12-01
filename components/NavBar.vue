<template lang="html">
  <div class="nav-bar" @click="close($event)">
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
      <div ref="cart" class="menu-item cart-container">
        <div @click="cartOpen = !cartOpen">
          <span>Cart</span>
          <span>(2)</span>
        </div>

        <transition name="slide-fade">
          <plt-cart @close="cartOpen = false" v-if="cartOpen"/>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cartOpen: false,
    }
  },
  mounted() {
    this.$nextTick(() => {
      window.addEventListener("click", this.close)
    })
  },
  beforeDestroy() {
    window.removeEventListener("click", this.close)
  },
  methods: {
    close(e) {
      if (!this.$refs.cart.contains(e.target) && this.cartOpen) {
        this.cartOpen = false
      }
    },
  }
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
  user-select: none;
}
.border-right {
  padding: 0 $space-m 0 0;
  border-right: 2px solid $font-color;
}
.slide-fade-enter-active {
  transition: all .1s ease;
}
.slide-fade-leave-active {
  transition: all .1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to{
  transform: translateY(-30px);
  opacity: 0;
}
.cart-container {
  font-weight: 600;
}
</style>
