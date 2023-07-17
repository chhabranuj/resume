<template>
  <div class="professionalExperience">
    <p class="title">
      <span style="color: #71c6dd">PROFESSIONAL</span> EXPERIENCE
    </p>
    <div class="companyAndJoiningDate">
      <p class="companyName">
        {{ toUppercase(data.companyName) }},
        <span style="color: #71c6dd">{{ toUppercase(data.place) }}</span>
      </p>
      <p class="joiningDate">
        {{ data.joiningDate }} ~
        <span style="color: #71c6dd">{{ data.endingDate }}</span>
      </p>
    </div>
    <p class="designation">{{ toUppercase(data.designation) }}</p>
    <ul class="work">
      <li
        style="color: #71c6dd; margin: 10px 0"
        v-for="item in data.work"
        :key="item"
      >
        <span class="workContent">{{ item }}</span>
      </li>
    </ul>
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
  margin-top: 0;
  font-family: "Akshar", sans-serif;
  letter-spacing: 2px;
  font-size: 22px;
  color: rgba(255, 255, 255, 0.6);
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
