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
      <Achievements class='ACHIEVEMENTS' v-bind:content='content'/>
      <hr class='divider'>
      <Achievements class='HACKATHON' v-bind:content='contentH'/>
    </div>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import AboutMe from './components/AboutMe.vue';
  import ProfessionalExperience from './components/ProfessionalExperience.vue';
  import Education from './components/Education.vue';
  import Skills from './components/Skills.vue';
  import Achievements from './components/Achievements.vue';

  export default {
    name: 'App',
    components: {
      Header,
      AboutMe,
      ProfessionalExperience,
      Education,
      Skills,
      Achievements,
    },
    data() {
      return {
        el: '#app',
        content: {
          title: 'achievements',
          achievements: [
            {
              award: 'comman review ratings',
              from: 'united health group',
              year: 'September 2019 - October 2021',
              description: 'Hold a rating of 4 Stars (2019) and a rating of 5 Stars (2020 and 2021) in yearly reviews.',
            },
            {
              award: 'star & spot awards',
              from: 'united health group',
              year: 'September 2019 - October 2021',
              description: 'Three times quarterly STAR award winner. Two times quarterly SPOT award winner.',
            },
            {
              award: 'sustaining edge award',
              from: 'united health group',
              year: 'March 2021',
              description: 'One time Sustaining Edge award winner.',
            },
            {
              award: 'performnance awards',
              from: 'united health group',
              year: 'September 2019 - October 2021',
              description: 'Been recognised by leaders, for providing KTs and presenting the product over the organisation (Topaz and Aquamarine awards). Countless number of bravo awards for performance, integrity and compassion.',
            },
          ] 
        },
        contentH: {
          title: 'hackathon',
          achievements: [
            {
              award: 'united health group',
              from: 'virtual global hackathon',
              year: 'August 2020',
              description: 'Won Global Hackathon (presented by Optum) in year 2020 for completing a challenge in Blockchain.',
            },
            {
              award: 'united health group',
              from: 'Enterprise clinical technology hackathon',
              year: 'December 2020',
              description: 'Won Enterprise Clinical Platform Hackathon (presented by ECT organisation), making a product to save costs.',
            },
            {
              award: 'wit-ace powered by ibm',
              from: 'sustainability using technology',
              year: 'June 2021',
              description: 'Won Popular Choice Award in WIT-ACE Hackathon, presented by IBM. Secured a place in Top 20, competing with over 5000 submissions.',
            },
            {
              award: 'united health group',
              from: 'virtual global hackathon',
              year: 'August 2021',
              description: 'Secured Runners up position in Global Hackthon (presented by Optum) in year 2021 for completing a challenge in Augmented Reality.',
            },
          ]
        },
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
