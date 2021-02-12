<template>
  <div class="todo-list-item">
    <w-checkbox v-model="item.isDone"/>
    <div class="todo-list-item_text">{{ item.text }}</div>
    <button class="dense" @click="emitDelete">Удалить</button>
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
  components: { WCheckbox },
  props: {
    item: Object
  },
  methods: {
    emitDelete(): void {
      this.$emit('delete', this.item.id);
    }
  }
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