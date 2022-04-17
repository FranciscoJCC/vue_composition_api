<template>
  <div>
    <p>{{ name }}</p>
    <p>{{ last_name }}</p>
    <p>{{ full_name }}</p>
    <p>{{ username }}</p>
  </div>
</template>

<script>
import { toRefs, computed, inject } from "vue";

export default {
  props: {
    name: String,
    last_name: String,
  },
  setup(props, { expose }) {
    const { name, last_name } = toRefs(props);

    const full_name = computed(() => {
      return `
            ${name.value} ${last_name.value}
        `;
    });

    const username = inject("username");

    expose({
      full_name,
    });

    return {
      full_name,
      username,
    };
  },
};
</script>

<style></style>
