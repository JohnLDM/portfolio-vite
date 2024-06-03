<script>
export default {
  name: 'Carousel',
  data() {
    return {
      technologies: [
        'bootstrap.png',
        'css.png',
        'html.png',
        'javascript.png',
        'laravel.png',
        'mysql.png',
        'php.svg',
        'sass.png',
        'vite.png',
        'vue.png',
      ],
    };
  },
};
</script>

<template>
  <section id="carousel">
    <!-- <ul>
      <li v-for="technology in technologies">
        <div class="cont-img">
          <img :src="`../../public/img/technologies/${technology}`" alt="img" />
        </div>
      </li>
    </ul> -->

    <div class="logos">
      <div class="logos-slide">
        <img
          v-for="technology in technologies"
          :src="`/img/logo/${technology}`"
          alt="img"
        />
      </div>
      <div class="logos-slide">
        <img
          v-for="technology in technologies"
          :src="`/img/logo/${technology}`"
          alt="img"
        />
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use '../assets/scss/style.scss' as *;

@keyframes slide {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(-100%);
  }
}

.logos {
  overflow: hidden;
  padding: 30px 0;
  white-space: nowrap;
  background-color: var(--custom-primary);

  // &:hover .logos-slide {
  //   animation-play-state: paused;
  //   cursor: pointer;
  // }

  .logos-slide {
    display: inline-block;
    animation: 30s slide infinite linear;
  }

  .logos-slide img {
    height: clamp(50px, 5vw, 100px);
    margin: 0 clamp(30px, 3vw, 80px);
  }
}
</style>
