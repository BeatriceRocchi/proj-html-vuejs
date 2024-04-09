<script>
import { goalsList } from "../assets/data/db_sectionGoals";
import { goalsListVisual } from "../assets/data/db_sectionGoals";
export default {
  data() {
    return {
      goalsList,
      goalsListVisual,
    };
  },
  methods: {
    getImagePath(img) {
      return new URL(`../assets/img/${img}`, import.meta.url).href;
    },
  },
};
</script>
<template>
  <section class="section_custom">
    <div class="container container_custom">
      <div class="row row-cols-2">
        <div class="col">
          <h3>
            We have been educating children for over fifteen years. Our goal is
            to create a place that engages each child.
          </h3>
          <p>
            Praesent arcu gravida vehicula est node maecenas loareet morbi a
            dosis luctus. Urna eget lacinia eleifend praesent luctus a arcu quis
            facilis venenatis aenean interdum.
          </p>
          <ul>
            <li
              class="d-flex align-items-center my-2"
              v-for="(goal, id) in goalsList"
              :key="id"
            >
              <img
                class="me-2"
                src="../assets/img/style_1.png"
                alt="Tick icon"
              />
              <p>{{ goal.text }}</p>
            </li>
          </ul>
        </div>
        <div class="col d-flex flex-wrap">
          <div
            v-for="item in goalsListVisual"
            :key="item.id"
            class="w-50 d-flex flex-column align-items-center text-center"
          >
            <div
              class="img_box d-flex align-items-center justify-content-center"
            >
              <img :src="getImagePath(item.img)" :alt="item.title" />
            </div>
            <h4>{{ item.title }}</h4>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../assets/scss/partials/variables";

ul {
  margin-top: 40px;
}

.img_box {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background-color: $color-white;
}
</style>
