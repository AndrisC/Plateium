<template lang="html">
  <div class="one-field">
    <div class="flex-wrapper">
      <label v-if="title">
        {{ title }}
      </label>
    </div>

    <tag
      ref="field"
      v-bind="computedBinds"
      class="field"
      @focus="scrollIntoView()"
    />
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
    },
  },
  data() {
    return {
      tag: 'input'
    }
  },
  computed: {
    computedBinds() {
      let obj = {
        ...this.$attrs,
        is: this.$attrs.tag || 'input',
      }
      if(this.$attrs.tag == 'textarea') obj['value.prop'] = this.$attrs.value

      return obj
    }
  },
  methods: {
    scrollIntoView() {
      if( !this.$props.scrollTofield ) return

      let tag = this.$refs.field
      tag.scrollIntoView({ behavior: "smooth", block: "center", inline: "nearest" })
    },
  }
}
</script>

<style lang="scss" scoped>
::placeholder {
  color: $font-color-lighter;
}
.flex-wrapper {
  display: flex;
}
.one-field {
  margin: $space-s 0 0 0;
  position: relative;

  label {
    position: relative;
    transition: all .3s;
    font-size: $paragraph-small;
    color: $font-color-lighter;
    font-weight: 400;
    padding: 0;
    margin: 0;
    display: flex;
  }
  &:hover {
    .edit {
      opacity: 1;
    }
  }
}
.field {
  height: 40px;
  padding: 0px $space-s;
  width: 100%;
  border: none;
  display: block;
  border-radius: $radius-default;
  outline: none;
  box-sizing: border-box;
  border: 2px solid $border-color;
  background: #fff;
  font-size: $paragraph;
  margin: $space-xs 0 0 0;
  transition: all .3s;
  &:focus {
    border: 2px solid $secondary-dark-200;
    background: #fff;
    box-shadow: 0px 0px 3px rgba($secondary-color, .5);
  }
}
textarea {
  min-height: 130px !important;
  padding: $space-s!important;
  resize: none;
}
</style>
