<template>
  <div class="body-block">
    <div class="wrapper">
      <div class="layout">
        <input placeholder="Текст задачи" v-model="taskText"/>
        <button>Добавить</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'body-block',
  data: () => ({
    taskText: ''
  })
});
</script>

<style lang="scss">
.body-block {
  flex-grow: 1;

  > .wrapper {
    margin: 0 auto;
    padding: 16px 0;
    width: 600px;
    height: 100%;
  }
}
</style>
