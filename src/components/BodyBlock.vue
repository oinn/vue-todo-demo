<template>
  <div class="body-block">
    <div class="wrapper">
      <div class="layout">
        <input placeholder="Текст задачи" v-model="taskText"/>
        <button class="blue">Добавить</button>
      </div>

      <div class="subtitle">Задачи</div>

      <div class="info">Список задач пуст</div>
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

  .info {
    font-size: 18px;
    font-style: italic;
    text-align: center;
  }
}
</style>
