<script>
export default {
  name: 'CardProject',
  props: {
    imagePath: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    technologies: {
      type: Array,
      required: true,
    },
    transition: {
      type: String,
      required: true,
    },
  },
  data() {
    return {};
  },
  components: {},
};
</script>

<template>
  <div :class="['custom-card-project d-flex', transition]">
    <div class="carousel border">
      <div class="cont-img">
        <img :src="imagePath" :alt="title" />
      </div>
    </div>
    <div class="cont-info">
      <h3 class="text-center">{{ title }}</h3>
      <p>{{ description }}</p>
      <h5>Used technologies:</h5>
      <ul class="m-0">
        <li v-for="(tech, index) in technologies" :key="index">
          <span>{{ tech }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

.custom-card-project {
  height: clamp(150px, 30vw, 10000px);
  width: 90%;
  background-color: var(--custom-tertiary);
  color: var(--custom-white);

  .carousel {
    width: 60%;

    .cont-img {
      width: 100%;
      height: 100%;
      overflow: hidden;

      img {
        width: 100%;
        object-fit: cover;
      }
    }
  }

  .cont-info {
    width: 40%;

    h3 {
      border: 1px solid green;
      font-size: clamp(12px, 3vw, 40px);
      font-weight: 800;
      padding: clamp(8px, 3vw, 20px) 0 clamp(5px, 2vw, 20px);
      margin: 0;
    }

    p {
      border: 1px solid red;
      font-size: clamp(8px, 1.5vw, 300px);
      text-align: center;
      // padding: 0 clamp(20px, 3vw, 50px);
      font-weight: 600;
      width: 90%;
      margin: 0 auto;
    }

    h5 {
      border: 1px solid gold;
      width: 90%;
      margin: 0 auto;
      padding-top: clamp(8px, 2vw, 20px);
      font-size: clamp(10px, 2vw, 40px);
    }

    ul {
      border: 1px solid royalblue;
      width: 100%;
      list-style-type: none;
      padding-left: clamp(8px, 2vw, 20px);

      li {
        border: 1px solid aquamarine;
        line-height: clamp(8px, 1.5vw, 300px);
        width: 90%;
        margin: 0 auto;

        span {
          font-size: clamp(8px, 1.5vw, 300px);
        }
      }
    }
  }
}
</style>
