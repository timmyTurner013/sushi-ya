<script setup lang="ts">
import { ref, onMounted } from "vue";
import axios from "axios";

const message = ref("sushi-ya");

onMounted(async () => {
  try {
    const response = await axios.get("http://localhost:3000");
    message.value = response.data;
  } catch (error) {
    console.error("Error fetching data: ", error);
  }
});
</script>

<template>
  <div>
    <h1>{{ message }}</h1>
  </div>
</template>
