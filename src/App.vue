<template>
  <div id="app">
    <header-block/>
    <body-block/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HeaderBlock from '@/components/HeaderBlock.vue';
import BodyBlock from '@/components/BodyBlock.vue';

export default Vue.extend({
  name: 'App',
  components: { HeaderBlock, BodyBlock }
});
</script>

<style lang="scss">
#app {
  height: 100%;
  display: flex;
  flex-direction: column;

  background: #FFFFFF;

  font-family: Calibri, sans-serif;
}
</style>
