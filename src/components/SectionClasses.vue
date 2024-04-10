<script>
import CardClass from "./partials/CardClass.vue";
import classList from "../assets/data/db_sectionClasses.js";
export default {
  components: {
    CardClass,
  },
  data() {
    return {
      classList,
    };
  },
};
</script>

<template>
  <section class="section_custom text-center">
    <div class="container container_custom">
      <!-- Upper section -->
      <h2>Our Classes</h2>
      <h5 class="mt_20 mb_30">
        Our preschool program has fout dedicated classes
      </h5>
      <img
        class="header_divider"
        src="../assets/img/header_divider.png"
        alt="---"
      />
      <div class="d-flex text-start">
        <h3 class="mb_60">
          We provided four classes with nine to twenty children each aged twelve
          month to five years of age.
        </h3>
        <p>
          Praesent arcu gravida vehicula est node maecenas loareet morbi a dosis
          luctus. Urna eget lacinia eleifend praesent luctus a arcu quis facilis
          venenatis. Aenean interdum, nibh vitae sodales, magna ante feugiat
          elit maecenas.
        </p>
      </div>
      <!-- /Upper section -->

      <!-- Lower section -->
      <div class="row row-cols-2 flex-wrap">
        <CardClass
          v-for="item in classList"
          :key="item.id"
          :itemElement="item"
        />
      </div>
      <!-- /Lower section -->
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../assets/scss/partials/variables";

h3 {
  width: 50%;
  padding-right: 16px;
}

p {
  width: 50%;
  padding-left: 16px;
  font-size: 1.1rem;
}
</style>
