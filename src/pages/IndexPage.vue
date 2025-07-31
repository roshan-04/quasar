<template>
  <q-page class="q-pa-md">
    <h5>Todo List</h5>

    <q-input v-model="newTask" label="Add Task" filled @keyup.enter="addTask" />
    <q-btn label="Add" @click="addTask" color="secondary" class="q-my-md" />

    <q-list bordered class="q-mt-md" v-if="todos.length">
      <q-item v-for="(todo, index) in todos" :key="index">
        <q-item-section>{{ index + 1 }}. {{ todo }}</q-item-section>
      </q-item>
    </q-list>

    <div v-else class="text-grey">No tasks added yet.</div>
  </q-page>
</template>

<script setup>
import { ref } from "vue";

const newTask = ref("");
const todos = ref([]);

function addTask() {
  if (newTask.value.trim()) {
    todos.value.push(newTask.value);
    newTask.value = "";
  }
}
</script>
