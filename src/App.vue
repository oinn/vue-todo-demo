<template>
  <div id="app">
    <header-block/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HeaderBlock from '@/components/HeaderBlock.vue';

export default Vue.extend({
  name: 'App',
  components: { HeaderBlock }
});
</script>

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;

  background: #FFFFFF;

  font-family: Calibri, sans-serif;
}
</style>
