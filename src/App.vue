<template>
  <div>
    <div>
      <button @click="showMenu = !showMenu">Menú</button>
      <transition name="fade">
        <MainMenu v-show="showMenu" />
      </transition>
    </div>
    <div>
      <MainModal />
    </div>
    <div>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
import MainMenu from "./components/MainMenu.vue";
import MainModal from "./components/MainModal.vue";

export default {
  name: "App",
  components: {
    MainMenu,
    MainModal,
  },
  data() {
    return {
      showMenu: false,
      text: "Hola vue",
    };
  },

  beforeCreate() {
    console.log("beforeCreate: ", this.$data, this.$el);
  },

  created() {
    console.log("created: ", this.$data, this.$el);
  },

  mounted() {
    console.log("mounted: ", this.$data, this.$el);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-leave-active,
.fade-enter-active {
  transition: opacity 0.5s ease;
}
</style>
