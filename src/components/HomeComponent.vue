<template>
  <div>{{ obj }}</div>
</template>

<script>
import { reactive, watch } from "vue";

export default {
  setup() {
    const obj = reactive({ counter: 0 });

    setInterval(() => {
      obj.counter++;
    }, 50000);

    watch(
      () => obj.counter,
      (value, old_value) => {
        console.log(value, old_value);
      }
    );

    return {
      obj,
    };
  },
};
</script>

<style></style>
