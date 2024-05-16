<script>
import Jumbotron from './Jumbotron.vue';
import TechCarousel from './TechCarousel.vue';
import About from './About.vue';
import Projects from './Projects.vue';

export default {
  name: 'Main',

  components: {
    Jumbotron,
    TechCarousel,
    About,
    Projects,
  },
};
</script>

<template>
  <main>
    <Jumbotron />
    <TechCarousel />
    <About />
    <Projects />
  </main>
</template>

<style lang="scss" scoped></style>
