<script>
import Jumbotron from './Jumbotron.vue';
import Slider from './Carousel.vue';
import About from './About.vue';

export default {
  name: 'Main',

  components: {
    Jumbotron,
    Slider,
    About,
  },
};
</script>

<template>
  <main>
    <Jumbotron />
    <Slider />
    <About />
    <Jumbotron />
  </main>
</template>

<style lang="scss" scoped></style>
