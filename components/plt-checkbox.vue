<template lang="html">
  <div class="flex-container">
    <label class="container">
      <input type="checkbox" :checked="value" v-bind="$attrs" v-on="computedListeners" />

      <span class="label">{{ label }}</span> <span class="checkmark"></span>
    </label>
  </div>
</template>

<script>
export default {
  props: {
    value: {},
    label: {
      type: String,
      default: "",
    },
  },
  computed: {
    computedListeners() {
      let lists = {...this.$listeners}

      delete lists.change,
      lists.input = event => {
        this.$emit("input", event.target.checked)
        this.$emit('change', event.target.checked)
      }

      return lists
    },
  },
  watch: {
    value() {
      this.suggestion.change = this.$props.value
    }
  }
}
</script>

<style lang="scss" scoped>
.flex-container {
  display: flex;

  &:hover {
    .edit {
      opacity: 1;
    }
  }
}
.container {
  margin: $space-s $space-s 0 0;
  display: block;
  position: relative;
  cursor: pointer;
  font-size: 16px;
  padding-left: 33px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  border-radius: $radius-default;

  span {
    display: block;
    color: $font-color-light;
    font-weight: 500;
    transition: all .3s;
  }
  input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
  }
}
.checkmark {
  transition: all .3s;
  position: absolute;
  top: 0;
  left: 0;
  height: 22px;
  width: 22px;
  border: 2px solid #c8c8c8;
  background: #fff;
  border-radius: $radius-default;
}
.container input:checked ~ .checkmark {
  color: $secondary-dark-200;
  border: 2px solid $secondary-dark-200;
}
.container input:checked ~ .checkmark:after {
  opacity: 1;
}
.container input:checked ~ .label {
  color: $secondary-dark-200;
}
.checkmark:after {
  content: "";
  position: absolute;
  opacity: 0;
}
.container .checkmark:after {
  left: 50%;
  top: 45%;
  width: 7px;
  height: 11px;
  border: solid $secondary-dark-200;
  border-width: 0 3px 3px 0;
  border-radius: 3px;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: translate(-50%, -50%) rotate(45deg);
}
</style>
