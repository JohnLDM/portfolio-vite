<script>
import CardAbout from './CardAbout.vue';

export default {
  name: 'About',
  data() {
    return {
      items: [
        { text: "I'm currently living in the beautiful country of italy" },
        {
          text: "I'm fascinated by brilliant minds and ideas, and how there ideas can became reality",
        },
      ],
    };
  },
  components: {
    CardAbout,
  },
};
</script>

<template>
  <section id="about">
    <h2 class="text-uppercase">About me</h2>
    <div class="about-container">
      <div class="first-row d-flex justify-content-center">
        <!-- picture -->
        <div class="cont-pic">
          <img src="/public/img/profile-pic.jpg" alt="" />
        </div>

        <!-- riga 1 col 2 -->
        <div class="custom-card">
          <p>
            I'm a Jr Full stack web developer, always passionate about
            technology and what's behind it
          </p>
        </div>
      </div>

      <div class="first-row d-flex justify-content-center">
        <CardAbout
          class=""
          v-for="(item, index) in items"
          :key="index"
          :text="item.text"
        />
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

#about {
  background-color: var(--custom-primary);

  h2 {
    color: var(--custom-white);
    font-size: clamp(40px, 8vw, 200px);
    line-height: clamp(70px, 10vw, 200px);
    font-weight: 800;
    text-align: center;
    padding-top: 100px;
  }

  .cont-pic {
    // margin-left: clamp(30px, 10vw, 300px);
    animation: shiftR linear;
    animation-timeline: view();
    height: clamp(150px, 30vw, 10000px);
    width: clamp(150px, 30vw, 10000px);
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10%;
    overflow: hidden;
    margin: clamp(20px, 5vw, 50px);

    img {
      height: 100%;
      object-fit: cover;
    }
  }

  .custom-card {
    // margin-right: clamp(30px, 10vw, 300px);
    animation: shiftL linear;
    animation-timeline: view();
    height: clamp(150px, 30vw, 10000px);
    width: clamp(150px, 30vw, 10000px);
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10%;
    overflow: hidden;
    background-color: var(--custom-primary);
    border: 4px solid var(--custom-white);
    color: var(--custom-white);
    margin: clamp(20px, 5vw, 50px);

    img {
      height: 100%;
      object-fit: cover;
    }

    p {
      text-transform: uppercase;
      font-size: clamp(10px, 2vw, 300px);
      text-align: center;
      padding: 0 clamp(20px, 3vw, 50px);
      font-weight: 600;
    }
  }

  .cont-text {
    animation: shiftL linear;
    animation-timeline: view();
  }
}

@keyframes shiftR {
  0% {
    transform: translateX(-350%);
  }
  40% {
    transform: translateX(0);
  }
}

@keyframes shiftL {
  0% {
    transform: translateX(300%);
  }
  40% {
    transform: translateX(0);
  }
}
</style>
