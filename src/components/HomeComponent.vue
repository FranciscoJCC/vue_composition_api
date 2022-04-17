<template>
  <div>{{ text }}</div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const text = ref("Hola mundo");

    return {
      text,
    };
  },
};
</script>

<style></style>
