<template>
  <div>{{ message }}</div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
const message = ref("");

fetch("/api/message").then((r) => {
  r.text().then((t) => {
    message.value = t;
  });
});
</script>
