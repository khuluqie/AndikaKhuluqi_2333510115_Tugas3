<template>
  <div class="add-task">
    <input v-model="newTask" placeholder="Tambahkan tugas baru" />
    <button @click="add">Tambah</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits(['addTask']);
const newTask = ref('');

function add() {
  if (newTask.value.trim()) {
    emit('addTask', newTask.value.trim());
    newTask.value = '';
  }
}
</script>

<style scoped>
.add-task {
  margin-bottom: 1rem;
  display: flex;
  gap: 10px;
}
input {
  flex: 1;
  padding: 8px;
  border-radius: 5px;
  border: 1px solid #ccc;
}
button {
  padding: 8px 16px;
  background-color: #007acc;
  color: white;
  border: none;
  border-radius: 5px;
}
button:hover {
  background-color: #005fa3;
}
</style>
