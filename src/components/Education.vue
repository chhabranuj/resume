<template>
  <div class="education">
    <p class="title">EDUCATION</p>
    <div class="educationDetailsParent" v-for="item in data" :key="item.degree">
      <div class="educationDetails">
        <p class="institute">
          <span style="color: #71c6dd">{{ toUppercase(item.institute) }}</span
          >, {{ toUppercase(item.universityName) }},
          <span style="color: #71c6dd">{{ toUppercase(item.state) }}</span>
        </p>
        <p class="years">
          <span style="color: #71c6dd">{{ item.startingYear }}</span> ~
          {{ item.finalYear }}
        </p>
      </div>
      <p class="degree">
        {{ toUppercase(item.degree) }}
        <span style="color: white">{{ item.grade }}</span>
      </p>
      <ul>
        <li style="color: #71c6dd">
          <span class="description">{{ item.description }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "EducationLayout",
  props: ["education"],
  data() {
    return {
      data: {},
      toUppercase(value) {
        return value.toUpperCase();
      },
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.education));
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Akshar&display=swap");
.education {
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

.educationDetailsParent {
  width: 100%;
  margin: 15px 0;
}
.educationDetails {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.institute {
  font-family: "Poppins", sans-serif;
  font-size: 28px;
  margin: 0;
}
.years {
  font-family: "Open Sans", sans-serif;
}
.degree {
  margin: 0 0 20px 0;
  font-family: "Akshar", sans-serif;
  letter-spacing: 1px;
  font-size: 22px;
  color: rgba(255, 255, 255, 0.6);
}

.description {
  color: white;
  font-family: "Open Sans", sans-serif;
  white-space: pre-line;
  font-size: medium;
  letter-spacing: 1px;
  line-height: 1.5;
  text-align: justify;
  font-weight: 300;
}
@media screen and (max-width: 900px) {
  .education {
    padding: 25% 0;
    min-height: auto;
  }
  .title {
    font-size: 35px;
    margin: 0 0 25px 0;
  }
  .educationDetails {
    align-items: flex-start;
    flex-direction: column;
  }
  .degree {
    font-size: 22px;
  }
}
</style>
