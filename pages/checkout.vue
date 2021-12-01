<template lang="html">
  <div class="container">
    <div class="extended-header"></div>

    <div class="checkout-container">
      <div class="title">
        <h4>Checkout</h4>
      </div>

      <div class="fields-container">
        <div class="side-by-side">
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
        </div>

        <div class="single">
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
        </div>

        <div class="side-by-side">
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
        </div>

        <div class="single">
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
        </div>

        <div class="side-by-side">
          <plt-input class="smaller-field" title="Field title" placeholder="Placeholder" />
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
        </div>

        <div class="side-by-side">
          <plt-input class="smaller-field" title="Field title" placeholder="Placeholder" />
          <plt-input class="plt-input" title="Field title" placeholder="Placeholder" />
        </div>

        <div class="checkbox-container">
          <plt-checkbox label="Billing address same as shipping address" />
        </div>
      </div>

      <div class="checkbox-container-bottom">
        <plt-checkbox label="* I accept the Terms of Use and Privacy policy" />
      </div>

      <div class="button-container">
        <plt-button @click="$router.push('/')">Send order</plt-button>
      </div>

      <div class="checkout-footer">
        <span>
          * Ac placerat vestibulum lectus mauris ultrices eros in cursus. Sit amet
          est placerat in. Non sodales neque sodales ut etiam sit amet. Posuere lorem
          ipsum dolor sit. Id cursus metus aliquam eleifend mi in nulla. Ut faucibus pulvinar
          elementum integer enim neque volutpat ac tincidunt. Sit amet volutpat consequat
          mauris nunc congue nisi vitae.
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.extended-header {
  background: $primary-color;
  height: 370px;
  width: 100%;
}
.checkout-container {
  background: #fff;
  border-radius: $radius-default;
  box-shadow: $box-shadow;
  padding: $space-m;
  max-width: 650px;
  margin-top: -300px;
  margin-bottom: 100px;
}
.title {
  margin-bottom: $space-s;
}
.fields-container {
  display: flex;
  width: 100%;
  flex-direction: column;
  padding-bottom: $space-m;
  margin: $space-s 0 $space-xs 0;
  border-bottom: 2px solid $border-color;
}
.side-by-side {
  display: flex;
  justify-content: space-between;
  grid-gap: $space-m;
}
.plt-input {
  width: 100%;
}
.smaller-field {
  width: 300px;
}
.field-wrapper {
  width: 260px;
}
.button-container {
  display: flex;
  justify-content: flex-end;
  padding-bottom: $space-s;
  margin-bottom: $space-m;
  border-bottom: 2px solid $border-color;
}
.checkbox-container {
  margin: $space-xs 0 0 0 ;
}
.checkbox-container-bottom {
  margin-bottom: $space-l;
}
.checkout-footer {
  color: $font-color-lighter;
  font-size: $paragraph-tiny;
}
</style>
