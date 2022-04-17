<template>
<div class='app'>
    <Header />
    <div class='contents'>
      <AboutMe />
      <hr class='divider'>
      <ProfessionalExperience />
      <hr class='divider'>
      <Education />
      <hr class='divider'>
    </div>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import AboutMe from './components/AboutMe.vue';
  import ProfessionalExperience from './components/ProfessionalExperience.vue';
  import Education from './components/Education.vue';
  import Skills from './components/Skills.vue';

  export default {
    name: 'App',
    components: {
      Header,
      AboutMe,
      ProfessionalExperience,
      Education,
      Skills,
    },
  }
</script>

<style scoped>
  .app {
    display: flex;
    width: 100%;
  }
  .contents {
    width: 80%;
    height: 100vh;
    overflow-y: scroll;
  }
  .contents::-webkit-scrollbar {
    display: none;
  }
  .divider {
    border: 0;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    width: 100%;
  }

  @media screen and (max-width: 900px) {
    .app{
      flex-direction: column;
    }
    .contents {
      width: 100%;
      height: auto;
    }
    .divider {
      width: 100%;
    }
  }
</style>
