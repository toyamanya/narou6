<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
const props = defineProps({
  cityName: {
    type: String,
    required: true,
  },
});
const cityInfo = ref();
onMounted(async () => {
  const res = await axios.get("/api/cities/" + props.cityName);
  cityInfo.value = res.data;
});
</script>

<template>
  <div>
    <h1>
      {{ cityName }}
    </h1>
    <div v-if="cityInfo">{{ cityInfo }}</div>
    <div v-else>街がみつかりませんでした</div>
  </div>
</template>
