<template>
  <div class="professionalExperience">
    <p class="title">
      <span style="color: #71c6dd">PROFESSIONAL</span> EXPERIENCE
    </p>
    <div
      class="professionalExperienceChild"
      v-for="item in data"
      :key="item.companyName"
    >
      <div class="companyAndJoiningDate">
        <p class="companyName">
          {{ toUppercase(item.companyName) }},
          <span style="color: #71c6dd">{{ toUppercase(item.place) }}</span>
        </p>
        <p class="joiningDate">
          {{ item.joiningDate }} ~
          <span style="color: #71c6dd">{{ item.endingDate }}</span>
        </p>
      </div>
      <p class="designation">{{ toUppercase(item.designation) }}</p>
      <p class="url" @click="redirect(item.url)">
        <md-icon
          class="fa fa-external-link"
          style="color: #71c6dd; margin-right: 10px; margin-top: 5px"
        ></md-icon>
        {{ item.url }}
      </p>
      <ul class="work">
        <li
          style="color: #71c6dd; margin: 10px 0"
          v-for="item in item.work"
          :key="item"
        >
          <span class="workContent">{{ item }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProfessionalExperienceLayout",
  props: ["professionalExperience"],
  data() {
    return {
      data: {},
      toUppercase(value) {
        return value.toUpperCase();
      },
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.professionalExperience));
  },
  methods: {
    redirect(url) {
      window.open(url);
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Akshar&display=swap");
.professionalExperience {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;
  margin: 0 5%;
  min-height: 100vh;
  color: white;
}
.title {
  font-family: "Poppins", sans-serif;
  font-size: 45px;
  margin: 0 0 20px 0;
}

.professionalExperienceChild {
  margin-bottom: 2rem;
}
.companyAndJoiningDate {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.companyName {
  font-family: "Poppins", sans-serif;
  font-size: 28px;
  letter-spacing: 1px;
  margin: 0;
}
.joiningDate {
  font-family: "Open Sans", sans-serif;
}
.designation {
  margin: 0;
  margin-bottom: 4px;
  font-family: "Akshar", sans-serif;
  letter-spacing: 2px;
  font-size: 22px;
  color: rgba(255, 255, 255, 0.6);
}

.url {
  font-family: "Open Sans", sans-serif;
  font-size: medium;
  font-weight: bolder;
  margin: 0;
  color: white;
  width: 85%;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  cursor: pointer;
}

.url:hover {
  color: #71c6dd;
}
.work {
  margin-top: 10px;
}
.workContent {
  font-family: "Open Sans", sans-serif;
  white-space: pre-line;
  font-size: medium;
  letter-spacing: 1px;
  line-height: 1.5;
  text-align: justify;
  color: white;
  font-weight: 300;
}
@media screen and (max-width: 900px) {
  .professionalExperience {
    min-height: auto;
    padding: 25% 0;
  }
  .title {
    font-size: 35px;
    margin: 0 0 25px 0;
  }
  .companyAndJoiningDate {
    align-items: flex-start;
    flex-direction: column;
  }
  .companyName {
    font-size: 22px;
  }
}
</style>
