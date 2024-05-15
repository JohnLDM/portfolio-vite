<script>
import Jumbotron from './Jumbotron.vue';
import Slider from './Carousel.vue';
import About from './About.vue';
import Projects from './Projects.vue';

export default {
  name: 'Main',

  components: {
    Jumbotron,
    Slider,
    About,
    Projects,
  },
};
</script>

<template>
  <main>
    <Jumbotron />
    <Slider />
    <About />
    <Projects />
    <Jumbotron />
  </main>
</template>

<style lang="scss" scoped></style>
