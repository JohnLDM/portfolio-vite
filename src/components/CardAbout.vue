<script>
export default {
  name: 'CardAbout',
  data() {
    return {};
  },
  components: {},

  props: {
    text: {
      type: String,
      required: true,
    },
  },
};
</script>

<template>
  <div class="custom-card2">
    <p>{{ text }}</p>
  </div>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

@keyframes fade {
  0% {
    opacity: 0;
  }
  30% {
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
}

.custom-card2 {
  animation: fade linear;
  animation-timeline: view();
  height: clamp(150px, 30vw, 10000px);
  width: clamp(150px, 30vw, 10000px);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10%;
  background-color: var(--custom-primary);
  border: 2px solid var(--custom-white);
  color: var(--custom-white);
  margin: clamp(20px, 5vw, 50px);

  p {
    text-transform: uppercase;
    font-size: clamp(10px, 2vw, 300px);
    text-align: center;
    padding: 0 clamp(20px, 3vw, 50px);
    font-weight: 600;
  }
}
</style>
