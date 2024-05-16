<script>
import CardProject from './CardProject.vue';

export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          videoPath: 'comus',
          title: 'Comus',
          description:
            'Food delivery web-app. Users can order food and restaurateurs sign up to add dishes to the menu.',
          technologies: ['VueJS', 'Laravel', 'MySQL'],
          transition: 'shiftR',
        },
        {
          videoPath: 'netflix',
          title: 'Streaming Web App',
          description:
            'Movie streaming web-app. Allows searching for movies and TV shows via API.',
          technologies: ['HTML', 'CSS', 'Javascript', 'VueJS'],
          transition: 'shiftL',
        },
        {
          videoPath: 'whatsapp',
          title: 'Messaging web-app',
          description:
            'Messaging web-app. Allows you to send and receive predefined messages.',
          technologies: ['HTML', 'CSS', 'Javascript', 'VueJS'],
          transition: 'shiftR',
        },
      ],
    };
  },
  components: {
    CardProject,
  },
};
</script>

<template>
  <section id="projects">
    <h2 class="text-uppercase">Projects</h2>
    <div class="cont-projects">
      <CardProject
        v-for="(project, index) in projects"
        :video-path="project.videoPath"
        :title="project.title"
        :description="project.description"
        :technologies="project.technologies"
        :transition="project.transition"
        :key="index"
      />
    </div>
  </section>
</template>

<style lang="scss">
@use '../assets/scss/style.scss' as *;

@keyframes shiftR {
  0% {
    transform: translateX(-100%);
  }
  30% {
    transform: translateX(0);
  }
}

@keyframes shiftL {
  0% {
    transform: translateX(100%);
  }
  30% {
    transform: translateX(0);
  }
}

#projects {
  background-color: var(--custom-primary);
  padding-bottom: 50px;

  h2 {
    color: var(--custom-white);
    font-size: clamp(40px, 8vw, 200px);
    line-height: clamp(70px, 10vw, 200px);
    font-weight: 800;
    text-align: center;
    padding-top: 100px;
  }

  .cont-projects {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: clamp(20px, 2vw, 50px);
  }

  .shiftR {
    animation: shiftR linear;
    animation-timeline: view();
    align-self: flex-start;
  }

  .shiftL {
    animation: shiftL linear;
    animation-timeline: view();
    align-self: flex-end;
  }
}
</style>
