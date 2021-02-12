<template>
  <div class="todo-list-item">
    <w-checkbox/>
    <div class="todo-list-item_text">Текст задачи</div>
    <button class="dense">Удалить</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import WCheckbox from '@/components/WCheckbox.vue';

interface ITodoListItem {
  id: number;
  text: string;
  isDone: boolean;
}

export default Vue.extend({
  name: 'todo-list-item',
  components: { WCheckbox }
});
</script>

<style lang="scss">
.todo-list-item {
  margin: 0 0 16px 0;
  display: flex;
  flex-direction: row;
  align-items: center;

  > .todo-list-item_text {
    padding: 0 16px;
    flex-grow: 1;

    font-size: 18px;
  }

  > button {
    margin: 0;
  }
}
</style>