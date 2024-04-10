<script>
import IconItem from "./partials/IconItem.vue";
import welcomeItemList from "../assets/data/db_sectionWelcome";

export default {
  data() {
    return {
      welcomeItemList,
    };
  },
  components: {
    IconItem,
  },
};
</script>

<template>
  <section class="section_custom text-center">
    <div class="container container_custom">
      <!-- Upper section -->
      <h2>Welcome to Fable</h2>
      <h5 class="mb_30 mt_15">Fable daycare, preschool, and kindergarten</h5>

      <img
        class="header_divider"
        src="../assets/img/header_divider.png"
        alt="---"
      />
      <!-- /Upper section -->

      <!-- Lower section -->
      <div class="d-flex align-items-center">
        <IconItem
          v-for="item in welcomeItemList"
          :key="item.id"
          :itemElement="item"
        />
      </div>
      <!-- /Lower section -->
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
