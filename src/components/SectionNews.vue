<script>
import CardNews from "./partials/CardNews.vue";
import newsList from "../assets/data/db_sectionNews.js";
import Btn from "./partials/Btn.vue";

export default {
  components: {
    CardNews,
    Btn,
  },
  data() {
    return {
      newsList,
    };
  },
};
</script>

<template>
  <section class="section_custom text-center">
    <div class="container container_custom">
      <h2>What's New</h2>
      <h5 class="mt_20 mb_30">Keep up to date with the latest news</h5>
      <img
        class="header_divider"
        src="../assets/img/header_divider.png"
        alt="---"
      />
      <div class="row row-cols-3 justify-content-between">
        <CardNews v-for="news in newsList" :key="news.id" :newsElement="news" />
      </div>
      <Btn
        class="mx-auto mt_40"
        :textButton="'go to blog'"
        :colorButton="'primary'"
      />
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
