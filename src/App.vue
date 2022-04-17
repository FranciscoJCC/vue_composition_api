<template>
  <div>
    <!-- <UserRepositories :user="'Diana'" /> -->
    <HomeComponent />
  </div>
</template>

<script>
/* import UserRepositories from "./components/UserRepositories.vue"; */
import HomeComponent from "./components/HomeComponent.vue";

export default {
  name: "App",
  components: {
    /* UserRepositories, */
    HomeComponent,
  },
  data() {
    return {
      showMenu: false,
      text: "Hola vue",
    };
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
