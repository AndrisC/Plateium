<template lang="html">
  <div class="one-field-select">
    <multiselect
      v-on="$listeners"
      v-bind="$attrs"
      @search-change="getInput"
      :value="value"
      @input="handleInput($event)"
    >
    <template slot="caret">
      <div>
        <div class="multiselect__select">
          <i class="fas fa-chevron-down"></i>
        </div>
      </div>
    </template>

      <div slot="noResult"><slot name="noResultSlot"></slot></div>
    </multiselect>
    <label v-if="title">{{ title }}</label>
  </div>
</template>

<script>
import Multiselect from "vue-multiselect"
export default {
  props: {
    title: {
      type: String,
    },
    value: {},
  },
  components: {
    Multiselect,
  },
  data() {
    return {
      errors: [],
      showErrors: false,
    }
  },
  methods: {
    handleInput(value) {
      this.$emit("input", value)
      this.$emit('change', value)
    },
    getInput(e) {
      this.$emit("searchChange", e)
    },
  },
  watch: {
    "$props.value": function() {
      this.handleInput(this.$props.value)
    },
  },
}
</script>

<style lang="scss">
.one-field-select {
  display: flex;
  flex-direction: column-reverse;
  flex-wrap: nowrap;
  justify-content: space-between;
  max-width: 400px;
  margin: $space-s $space-m $space-s 0;

  label {
    transition: all .3s;
    font-size: $paragraph-small;
    color: $font-color;
    font-weight: 400;
    display: flex;
    flex-wrap: nowrap;
    margin: 0 $space-xxs $space-xs $space-xxs;
    width: 100%;
  }
}
.multiselect {
  position: relative;
  min-height: 40px;
  width: 100%;
  cursor: pointer;
}
.multiselect__tags {
  overflow: hidden;
  min-height: 40px;
  padding: 8px 4px 0 8px;
  border-radius: $radius-default;
  border: 2px solid $border-color;
  background: #fff;
  transition: all .3s ease, background 0s;
}
.multiselect__select {
  position: absolute;
  width: 24px;
  background: none;
  right: $space-xs;
  top: 11px;
  text-align: center;
  cursor: pointer;
  transition: transform .3s ease;
  color: $font-color-lighter;
  font-size: $paragraph-small;
}
.multiselect__tag {
  position: relative;
  display: inline-block;
  padding: $space-xxs 25px $space-xxs $space-xs;
  border-radius: $radius-default;
  margin: 0 $space-xs 0 0;
  line-height: 1;
  color: #fff;
  background: $secondary-dark-200;
  white-space: nowrap;
  overflow: hidden;
  max-width: 100%;
  text-overflow: ellipsis;
  animation: fade .3s cubic-bezier(0.41, 0.26, 0.2, 0.62);
}
.multiselect__tag-icon {
  cursor: pointer;
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
  font-weight: 700;
  font-style: initial;
  width: 22px;
  text-align: center;
  line-height: 22px;
  transition: all .3s ease;
  border-radius: $radius-default;
}
.multiselect__tag-icon:after {
  content: "×";
  color: #fff;
  font-size: $paragraph-small;
}
.multiselect__tag-icon:focus,
.multiselect__tag-icon:hover {
  background: $secondary-dark-200;
}
.multiselect__content-wrapper {
  position: absolute;
  z-index: 2;
  width: 100%;
  max-height: 240px;
  background: #fff;
  overflow-y: scroll;
  top: $space-l;
  box-shadow: $box-shadow;
  border-radius: $radius-default;
  margin-bottom: $space-m;
  animation: slideDown .1s forwards;
}

.multiselect__content {
  width: 100%;
  list-style: none;
  padding: 0;
  margin: 0;
}

.multiselect__element {
  cursor: pointer;
  font-size: $paragraph-small;
  &:hover {
    background: $secondary-light-700;
  }
}

.multiselect__option {
  padding: $space-xs;
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  white-space: nowrap;
  transition: all .3s;
}

.multiselect__option--highlight {
  background: #fff;
}
.multiselect__option--highlight:hover {
  background: $secondary-light-800;
}

.multiselect__option--highlight:after {
  content: attr(data-select);
  background: #fff;
}

.multiselect__option--selected {
  background: $secondary-light-700;
  color: #35495e;
  font-weight: 600;
}

.multiselect__option--selected:after {
  content: attr(data-selected);
  color: #35495e;
}

.multiselect__option--selected.multiselect__option--highlight {
  background: $error-color;
  color: #fff;
}

.multiselect__option--selected.multiselect__option--highlight:after {
  background: $error-color;
  content: attr(data-deselect);
  color: #fff;
}

.multiselect--active {
  .multiselect__select {
    transform: rotateZ(180deg);
  }
  .multiselect__tags {
    background: #fff;
    min-height: 40px;
    border-color: $secondary-dark-200;
  }
  .multiselect__select {
    background: #fff;
  }
  ~ label {
    color: $secondary-dark-200;
  }
  .multiselect__tag {
    margin: 0 $space-xs $space-xs 0;
  }
}

.multiselect__input,
.multiselect__single {
  display: inline-block;
  white-space: nowrap;
  border: none;
  outline: none;
  font-size: $paragraph-small;
  transition: border .3s ease;
  box-sizing: border-box;
  vertical-align: top;
}

.multiselect__input {
  padding: 0 0 $space-xxs 0;
}

.multiselect__placeholder {
  color: $font-color-lighter;
  white-space: nowrap;
  font-size: $paragraph-small;
}
.icon-margin-right {
  margin-right: $space-xxs;
}
@keyframes spinning {
  from {
    transform: rotate(0);
  }
  to {
    transform: rotate(2turn);
  }
}
@keyframes fade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
:focus {
  outline: none;
}
.multiselect--disabled {
  background: #ededed;
  pointer-events: none;
  opacity: 0.6;
}
.multiselect--disabled .multiselect__current,
.multiselect--disabled .multiselect__select {
  background: #ededed;
  color: #a6a6a6;
}
.multiselect__option--disabled {
  background: #ededed !important;
  color: #a6a6a6 !important;
  cursor: text;
  pointer-events: none;
}
.multiselect__option--disabled.multiselect__option--highlight {
  background: #dedede;
}

@keyframes fade {
  0% {
    opacity: 0
  }
  100% {
    opacity: 1
  }
}
@keyframes slideDown {
  0% {
    margin-top: -$space-m;
    opacity: 0;
  }
  100% {
    margin-top: 0;
    opacity: 1;
  }
}
</style>
