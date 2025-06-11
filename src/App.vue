<template>
  <div class="app">
    <h1>🧠 Aplikasi To-do dengan Vue 3</h1>
    <TaskList :tasks="tasks" @toggleTask="toggleTask">
      <AddTask @addTask="addTask" />
    </TaskList>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import TaskList from './components/TaskList.vue';
import AddTask from './components/AddTask.vue';

const tasks = ref([
  { text: 'Belajar Vue 3', done: false },
  { text: 'Kerjakan tugas nested component', done: false },
]);

function toggleTask(index) {
  tasks.value[index].done = !tasks.value[index].done;
}

function addTask(text) {
  tasks.value.push({ text, done: false });
}
</script>

<style scoped>
.app {
  max-width: 600px;
  margin: 2rem auto;
  padding: 1rem;
  font-family: 'Segoe UI', sans-serif;
}
h1 {
  text-align: center;
  color: #333;
  margin-bottom: 2rem;
}
</style>
