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
  <div class="container container_custom">
    <section class="section_custom">
      <h2>Welcome to Fable</h2>
      <h5>Fable daycare, preschool, and kindergarten</h5>
      <img
        class="header_divider"
        src="../assets/img/header_divider.png"
        alt="---"
      />
      <div class="d-flex align-items-center">
        <IconItem
          v-for="item in welcomeItemList"
          :key="item.id"
          :itemElement="item"
        />
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
.header_divider {
  margin: 30px 0 65px;
}
</style>
