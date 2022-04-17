<template>
  <div>
    <p>{{ name }}</p>
    <p>{{ last_name }}</p>
    <p>{{ full_name }}</p>
    <p>{{ username }}</p>
    <button ref="btn">Click!</button>
  </div>
</template>

<script>
import { toRefs, computed, inject, ref, watch } from "vue";

export default {
  props: {
    name: String,
    last_name: String,
  },
  setup(props, { expose }) {
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

    expose({
      full_name,
    });

    return {
      full_name,
      username,
      btn,
    };
  },
};
</script>

<style></style>
