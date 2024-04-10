<script>
import Navbar from "./partials/Navbar.vue";

export default {
  components: {
    Navbar,
  },
};
</script>

<template>
  <header class="container container_custom d-flex justify-content-between">
    <img class="logo" src="../assets/img/logo.png" alt="Logo Fable" />
    <Navbar />
  </header>
</template>

<style lang="scss" scoped>
header {
  height: 125px;

  .logo {
    width: 185px;
  }
}
</style>
