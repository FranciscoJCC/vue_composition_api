<template>
  <div>
    <p>{{ name }}</p>
    <p>{{ last_name }}</p>
    <p>{{ full_name }}</p>
  </div>
</template>

<script>
import { toRefs, computed } from "vue";

export default {
  props: {
    name: String,
    last_name: String,
  },
  setup(props) {
    const { name, last_name } = toRefs(props);

    const full_name = computed(() => {
      return `
            ${name.value} ${last_name.value}
        `;
    });

    return {
      full_name,
    };
  },
};
</script>

<style></style>
