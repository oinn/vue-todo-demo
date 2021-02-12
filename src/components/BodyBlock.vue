<template>
  <div class="body-block">
    <div class="wrapper">
      <div class="layout">
        <input placeholder="Текст задачи" v-model="taskText"/>
        <button class="blue" @click="addTask">Добавить</button>
      </div>

      <div class="subtitle">Задачи</div>

      <div v-if="!items.length" class="info">Список задач пуст</div>

      <todo-list-item
        v-for="item in items" :key="item.id"
        :item="item"
        @delete="handleDelete"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import TodoListItem from '@/components/TodoListItem.vue';

interface ITodoListItem {
  id: number;
  text: string;
  isDone: boolean;
}

export default Vue.extend({
  name: 'body-block',
  components: { TodoListItem },
  data: () => ({
    taskText: '',
    items: [] as ITodoListItem[]
  }),
  computed: {
    nextTaskId(): number {
      return (this.items[this.items.length - 1]?.id || 0) + 1;
    }
  },
  methods: {
    addTask(): void {
      if (!!this.taskText.trim()) {
        this.items.push({
          id: this.nextTaskId,
          text: this.taskText,
          isDone: false
        });

        this.taskText = '';
      }
    },
    handleDelete(id: number): void {
      const index = this.items.findIndex((item) => item.id === id);
      this.items.splice(index, 1);
    }
  }
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
