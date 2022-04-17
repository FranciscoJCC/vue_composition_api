<template>
  <div>
    <p>{{ name }}</p>
    <p>{{ last_name }}</p>
    <p>{{ full_name }}</p>
    <p>{{ username }}</p>
    <button ref="btn">Click!</button>
  </div>
</template>

<script setup>
import {
  defineProps,
  defineExpose,
  toRefs,
  computed,
  inject,
  ref,
  watch,
} from "vue";

const props = defineProps({
  name: String,
  last_name: String,
});

//Props
const { name, last_name } = toRefs(props);

//Computed
const full_name = computed(() => {
  return `
            ${name.value} ${last_name.value}
        `;
});

//Inject
const username = inject("username");

//refs, como el setup se ejecuta antes de ser montado el componente
//La constante button siempre es null, aún no se puede acceder al DOM
// o al this.
const btn = ref(null);
console.log(btn.value);
watch(btn, (value) => {
  console.log(value);
});

defineExpose({
  full_name,
});
</script>

<style></style>
