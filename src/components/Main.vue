<script>
import Hero from "./partials/Hero.vue";
import CtaSeparator from "./partials/CtaSeparator.vue";
import Gallery from "./partials/Gallery.vue";
import SectionWelcome from "./SectionWelcome.vue";
import SectionOverview from "./SectionOverview.vue";
import SectionNumbers from "./SectionNumbers.vue";
import SectionClasses from "./SectionClasses.vue";
import SectionGoals from "./SectionGoals.vue";
import SectionStaff from "./SectionStaff.vue";
import SectionQuote from "./SectionQuote.vue";
import SectionNews from "./SectionNews.vue";

export default {
  components: {
    Hero,
    CtaSeparator,
    Gallery,
    SectionWelcome,
    SectionOverview,
    SectionNumbers,
    SectionClasses,
    SectionGoals,
    SectionStaff,
    SectionQuote,
    SectionNews,
  },
};
</script>

<template>
  <main>
    <Hero />
    <CtaSeparator
      :CtaTitle="'How to Enroll Your Child to a Class?'"
      :CtaButtonText="'Learn more'"
    />
    <SectionWelcome />
    <SectionOverview class="bg_grey" />
    <SectionNumbers />
    <SectionClasses />
    <SectionGoals class="bg_grey" />
    <Gallery />
    <CtaSeparator
      :CtaTitle="'See Our Kindergarten Photo Gallery!'"
      :CtaButtonText="'View Gallery'"
    />
    <SectionStaff />
    <SectionQuote />
    <SectionNews />
  </main>
</template>

<style lang="scss" scoped></style>
