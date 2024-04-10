<script>
import CardStaff from "./partials/CardStaff.vue";
import staffList from "../assets/data/db_sectionStaff.js";
export default {
  components: {
    CardStaff,
  },
  data() {
    return {
      staffList,
    };
  },
};
</script>

<template>
  <section class="section_custom text-center">
    <div class="container container_custom">
      <!-- Upper section -->
      <h2>Meet Our Staff</h2>
      <h5 class="mt_20 mb_30">
        With education and experience in early childhood care
      </h5>
      <img
        class="header_divider"
        src="../assets/img/header_divider.png"
        alt="---"
      />
      <div class="d-flex text-start">
        <h3 class="mb_60">
          Our staff consists of three teachers and one assistant with experience
          in early childhood care.
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
        <CardStaff
          v-for="staff in staffList"
          :key="staff.id"
          :staffElement="staff"
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
  padding-right: 25px;
}

p {
  width: 50%;
  padding-left: 15px;
  font-size: 1.1rem;
}
</style>
