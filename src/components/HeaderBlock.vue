<template>
  <div class="header-block" :class="{ teal: isOwner }">
    <h1 class="title">{{ greeting }}</h1>
    <input placeholder="Введите свое имя" v-model="userName"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'header-block',
  data: () => ({
    userName: ''
  }),
  computed: {
    isOwner(): boolean {
      return this.userName === 'Леонид';
    },
    greeting(): string {
      if (this.isOwner)
        return 'Насяльника присла';
      return this.userName.trim().length > 0
        ? `Привет, ${this.userName}`
        : 'Привет'
    }
  }
});
</script>

<style lang="scss">
@import "@/styles/variables.scss";

.header-block {
  padding: 32px 0 0 0;
  height: 200px;
  display: flex;
  flex-direction: column;

  background: $blue-lighten;

  color: $white;

  &.teal {
    background: $teal-lighten;

    > input {
      border-color: $teal;
    }
  }
}
</style>
