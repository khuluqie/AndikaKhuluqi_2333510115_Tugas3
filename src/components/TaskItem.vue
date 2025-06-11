<template>
  <div class="task-item" :class="{ done: task.done }">
    <p>{{ task.text }}</p>
    <button @click="toggleStatus">
      {{ task.done ? 'Batal Selesai' : 'Tandai Selesai' }}
    </button>
  </div>
</template>

<script setup>
defineProps(['task']);
const emit = defineEmits(['toggle']);

function toggleStatus() {
  emit('toggle');
}
</script>

<style scoped>
.task-item {
  background-color: #fff;
  padding: 1rem;
  border-radius: 8px;
  margin-bottom: 10px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.task-item.done p {
  text-decoration: line-through;
  color: gray;
}
button {
  background-color: #28a745;
  border: none;
  color: white;
  padding: 6px 12px;
  border-radius: 5px;
  cursor: pointer;
}
button:hover {
  background-color: #218838;
}
</style>
