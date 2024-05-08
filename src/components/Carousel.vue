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
  <section>
    <ul>
      <li v-for="technology in technologies">
        <div class="cont-img">
          <img :src="`../../public/img/technologies/${technology}`" alt="img" />
        </div>
      </li>
    </ul>
  </section>
</template>

<style scoped lang="scss">
@use '../assets/scss/style.scss' as *;

.cont-img {
  width: 100px;

  img {
    width: 100%;
  }
}
</style>
