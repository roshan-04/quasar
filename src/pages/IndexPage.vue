<template>
  <q-page class="testing">
    <h4>{{ message }}</h4>

    <!-- you use v-model here to binding the data and message -->
    <input v-model="message" label="Type something" filled class="testing" />
    <q-btn color="primary" label="Clear" v-on:click="message = ''" />
  </q-page>
</template>

<script setup>
import { ref } from "vue";

const message = ref("Welcome Roshan Yadav");
</script>

<style></style>
