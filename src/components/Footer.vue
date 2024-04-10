<script>
import { archivesList } from "../assets/data/db_footer.js";
import { featuresList } from "../assets/data/db_footer.js";
import { socialLists } from "../assets/data/db_footer.js";
import newsList from "../assets/data/db_sectionNews.js";
import CardFooter from "./partials/CardFooter.vue";

export default {
  components: {
    CardFooter,
  },
  data() {
    return {
      archivesList,
      featuresList,
      socialLists,
      newsList,
    };
  },
  methods: {
    getImagePath2(img) {
      return new URL(`../assets/img/${img}.png`, import.meta.url).href;
    },
  },
};
</script>

<template>
  <footer>
    <div class="upper_footer section_custom">
      <div class="container container_custom">
        <div class="row row-cols-4 g-4">
          <div class="col">
            <h5>about us</h5>
            <p>
              Ellipsis magna a nulla elite forte maecenas est elementum magna
              etos interdum movum morbi vehicula morbi.
            </p>
            <img
              class="logo"
              src="../assets/img/logo_footer.png"
              alt="Fable logo"
            />
          </div>
          <div class="col">
            <h5>archives</h5>
            <div
              class="article_box"
              v-for="(item, id) in archivesList"
              :key="id"
            >
              <span class="text-uppercase">{{ item.date }}</span>
              <span> ({{ item.articlesLists.length }})</span>
            </div>
          </div>
          <div class="col">
            <h5>our features</h5>
            <p>
              Nunc gravida rutrum mauris vehin hasellus ac pretium augue vivamul
              lacus ligul mattis ac vene:
            </p>
            <ul>
              <li
                class="d-flex align-items-center my-2"
                v-for="(item, id) in featuresList"
                :key="id"
              >
                <img
                  class="me-2"
                  src="../assets/img/style_4_alt.png"
                  alt="Tick icon"
                />
                <p class="m-0">{{ item.text }}</p>
              </li>
            </ul>
          </div>
          <div class="col">
            <h5>recent posts</h5>
            <CardFooter
              class="mb-4"
              v-for="item in newsList"
              :key="item.id"
              :newsElement="item"
            />
          </div>
        </div>
      </div>
    </div>
    <div class="lower_footer">
      <ul class="d-flex justify-content-center">
        <li
          class="square_box d-flex align-items-center justify-content-center"
          v-for="(item, id) in socialLists"
          :key="id"
        >
          <a href="#"><img :src="getImagePath2(item)" :alt="item" /></a>
        </li>
      </ul>
      <p class="text-center">
        © Fable - Children Kindergarten Wordpress Theme by QuanticalLabs
      </p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@import "../assets/scss/partials/variables";

.upper_footer {
  background-image: url(../assets/img/pattern.png);

  h5 {
    color: $color-white;
    text-transform: uppercase;

    &::after {
      content: "";
      display: block;
      width: 50px;
      background-color: $color-tertiary;
      height: 1px;
      margin-top: 10px;
      margin-bottom: 20px;
    }
  }

  p {
    color: rgba($color-white, 50%);
    margin-bottom: 20px;
    font-size: 0.9rem;
  }

  .logo {
    width: 180px;
  }

  .article_box {
    color: rgba($color-white, 50%);
    font-size: 0.9rem;
    padding: 10px;
    margin-bottom: 5px;
    border: 1px solid rgba($color-white, 50%);
  }
}

.lower_footer {
  padding: 30px 0;

  .square_box {
    background-color: $color-primary;
    width: 40px;
    aspect-ratio: 1;
    margin: 0px 2px 30px;
  }

  p {
    font-size: 0.8rem;
  }
}
</style>
