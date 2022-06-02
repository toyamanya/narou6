<script setup>
import HelloWorld from "../components/HelloWorld.vue";
import { ref } from "vue";
import router from "../router";

const cityname = ref("");
const displayCity = () => router.push(`/city/${cityname.value}`);
</script>

<template>
  <img alt="Vue logo" src="../assets/logo.png" />
  <hello-world msg="Hello Vue 3 + Vite" />
  <input v-model="cityname" type="text" />
  <button @click="displayCity">表示する</button>
</template>
