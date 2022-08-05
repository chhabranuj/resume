<template>
<div id='app'>
    <Header @clicked='getItemName' />
    <div class='contents'>
      <AboutMe class='ABOUT ME'/>
      <hr class='divider'>
      <ProfessionalExperience class='PROFESSIONAL EXPERIENCE'/>
      <hr class='divider'>
      <Education class='EDUCATION'/>
      <hr class='divider'>
      <Skills class='SKILLS'/>
      <hr class='divider'>
      <Projects class='PROJECTS' v-bind:content='content'/>
      <hr class='divider'>
    </div>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Skills from './components/Skills.vue';
  import AboutMe from './components/AboutMe.vue';
  import Projects from './components/Projects.vue';
  import Education from './components/Education.vue';
  import ProfessionalExperience from './components/ProfessionalExperience.vue';

  export default {
    name: 'App',
    components: {
      Header,
      AboutMe,
      ProfessionalExperience,
      Education,
      Skills,
      Projects,
    },
    data() {
      return {
        el: '#app',
        content: {
          title: 'projects',
          projects: [
            {
              title: 'Pen Down On Paper',
              url: 'https://pendownonpaper.netlify.app/',
              year: 'January 2022',
              description: 'Pendownonpaper is a wallpaper website.',
            },
            {
              title: 'HitchDoc',
              url: 'https://hitchdoc.netlify.app/',
              year: 'July 2022',
              description: 'Hitchdoc is a document saver website.',
            },
          ] 
        }
      }
    },
    methods: {
      getItemName(value) {
        const ele = this.$el.getElementsByClassName(value)[0];
        ele.scrollIntoView({behavior: 'smooth'});
      }
    }
  }
</script>

<style scoped>
  #app {
    display: flex;
    width: 100%;
  }
  .contents {
    width: calc(100% - 300px);
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
    #app{
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
