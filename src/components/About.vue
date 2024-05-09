<script>
export default {
  name: 'About',
  data() {
    return {};
  },
  components: {},
};
</script>

<template>
  <section id="about">
    <h2>About</h2>
    <div class="about-container d-flex">
      <div class="cont-pic border border-danger">
        <img src="/public/img/profile-pic.jpg" alt="" />
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

@keyframes shift {
  0% {
    transform: translateX(-100%);
  }
  40% {
    transform: translateX(0);
  }
}

.cont-pic {
  margin-left: clamp(30px, 10vw, 300px);
  animation: shift linear;
  animation-timeline: view();
  height: clamp(150px, 30vw, 10000px);
  width: clamp(150px, 30vw, 10000px);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10%;
  overflow: hidden;

  img {
    height: 100%;
    object-fit: cover;
  }
}
</style>
