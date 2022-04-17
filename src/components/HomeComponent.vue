<template>
  <div>
    <p>{{ name }}</p>
    <p>{{ last_name }}</p>
    <p>{{ full_name }}</p>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const name = ref("Francisco");
    const last_name = ref("Cervantes");

    const full_name = computed(() => {
      return `
            ${name.value} ${last_name.value}
        `;
    });

    return {
      name,
      last_name,
      full_name,
    };
  },
};
</script>

<style></style>
