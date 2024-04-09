<script>
import IconItem from "./partials/IconItem.vue";
import RectangularMenu from "./partials/RectangularMenu.vue";
import numbersItemList from "../assets/data/db_sectionNumbers";

export default {
  data() {
    return {
      numbersItemList,
    };
  },
  components: {
    IconItem,
    RectangularMenu,
  },
};
</script>

<template>
  <section id="section_numbers">
    <div
      class="container container_custom h-100 d-flex flex-column justify-content-between"
    >
      <div class="d-flex align-items-center">
        <IconItem
          v-for="item in numbersItemList"
          :key="item.id"
          :itemElement="item"
          :itemType="'border'"
        />
      </div>
      <div class="d-flex justify-content-center">
        <RectangularMenu :itemNum="6" :itemSelected="1" :itemColor="'white'" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#section_numbers {
  padding: 80px 0 0;
  height: 525px;
  background-image: url(../assets/img/parallax_01.jpg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
</style>
