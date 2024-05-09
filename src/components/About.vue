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
    <div class="cont-pic border border-danger">
      <img src="/public/img/profile-pic.jpg" alt="" />
    </div>
  </section>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

@keyframes shift {
  0% {
    transform: translateX(-100%);
  }
  50% {
    transform: translateX(0);
  }
}

.cont-pic {
  margin-left: 300px;
  animation: shift linear;
  animation-timeline: view();
  height: 400px;

  img {
    height: 100%;
  }
}
</style>
