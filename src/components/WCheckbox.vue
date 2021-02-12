<template>
  <div class="w-checkbox" :class="{ checked: value }" @click="toggle"/>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'w-checkbox',
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    toggle(): void {
      this.$emit('input', !this.value);
    }
  }
});
</script>

<style lang="scss">
@import "@/styles/variables.scss";

.w-checkbox {
  height: 24px;
  width: 24px;

  background: $white;
  border: 2px solid $black;
  border-radius: 4px;
  cursor: pointer;

  &:hover {
    border-color: $blue;
  }

  &.checked {
    background-color: $blue;
    border-color: $blue;
    box-shadow: inset 0 0 1px 1px $white;
  }
}
</style>
