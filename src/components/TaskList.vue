<template>
  <div class="task-list">
    <h2>📋 Daftar Tugas</h2>
    <slot />
    <div v-if="tasks.length === 0">Belum ada tugas.</div>
    <TaskItem
      v-for="(task, index) in tasks"
      :key="index"
      :task="task"
      @toggle="toggleTask(index)"
    />
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';
import TaskItem from './TaskItem.vue';

const props = defineProps(['tasks']);
const emit = defineEmits(['toggleTask']);

function toggleTask(index) {
  emit('toggleTask', index);
}
</script>

<style scoped>
.task-list {
  background-color: #f0f8ff;
  padding: 1.5rem;
  border-radius: 12px;
  box-shadow: 0 3px 6px rgba(0,0,0,0.1);
}
h2 {
  margin-bottom: 1rem;
  color: #007acc;
}
</style>
