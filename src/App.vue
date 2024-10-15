<script setup lang="ts">
import { ref } from "vue";
import axios from "axios";

const apiBaseUrl = import.meta.env.VITE_API_BASE_URL;

// Reactive variables
const data = ref();
const error = ref();
const loading = ref();

// Fetch data
const fetchData = async () => {
  loading.value = true;
  try {
    const res = await axios.get(`${apiBaseUrl}/collections/members/records`);
    data.value = res.data;
    console.log(data.value);
  } catch (err) {
    error.value = err;
  } finally {
    loading.value = false;
  }
};
</script>

<template>
  <h1 class="text-red-500">hello</h1>
  <h2>hai</h2>
  <button @click="fetchData">button</button>
</template>

<style scoped></style>
