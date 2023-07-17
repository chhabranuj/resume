<template>
  <div class="projects">
    <p class="title">PROJECTS</p>
    <div class="awards" v-for="item in data" :key="item.description">
      <div class="titleAndTime">
        <p class="projectName">
          {{ toUppercase(item.title) }}
        </p>
        <p class="time">
          <span>{{ item.startDate }} ~ </span>
          <span style="color: #71c6dd">{{ item.endDate }}</span>
        </p>
      </div>
      <a class="url" :href="`${item.url}`" target="_blank"
        ><md-icon
          class="fa fa-external-link"
          style="color: #71c6dd; margin-right: 10px"
        ></md-icon
        >{{ item.url }}</a
      >
      <ul>
        <li
          style="color: #71c6dd; margin: 10px 0"
          v-for="items in item.description"
          :key="items"
        >
          <span class="description">{{ items }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectsLayout",
  props: ["projects"],
  data() {
    return {
      data: {},
      toUppercase(value) {
        return value.toUpperCase();
      },
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.projects));
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Akshar&display=swap");
.projects {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;
  margin: 5%;
  min-height: 100vh;
  color: white;
}
.title {
  font-family: "Poppins", sans-serif;
  font-size: 45px;
  margin: 0 0 20px 0;
}
.awards {
  margin: 8px 0;
  width: 100%;
}
.titleAndTime {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.projectName {
  font-family: "Poppins", sans-serif;
  font-size: 25px;
  margin-bottom: 5px;
  color: #71c6dd;
}
.time {
  font-family: "Open Sans", sans-serif;
}
.url {
  font-family: "Open Sans", sans-serif;
  font-size: medium;
  font-weight: bolder;
  margin-top: 5px;
  color: white;
  text-decoration: none;
}

.url:hover {
  color: #71c6dd;
}
.description {
  font-weight: 300;
  color: white;
  width: 75%;
  font-family: "Open Sans", sans-serif;
  white-space: pre-line;
  font-size: medium;
  letter-spacing: 1px;
  line-height: 1.5;
  text-align: justify;
}
.divider {
  border: 0;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  width: 100%;
}
@media screen and (max-width: 900px) {
  .projects {
    min-height: auto;
    padding: 25% 0;
  }
  .mobileHeight {
    padding-bottom: 15%;
  }
  .title {
    font-size: 35px;
    margin: 0 0 15px 0;
  }
  .titleAndTime {
    align-items: flex-start;
    flex-direction: column;
  }
  .projectName {
    font-size: 20px;
  }
  .description {
    font-family: "Open Sans", sans-serif;
    line-height: 1.5;
    letter-spacing: 1px;
    font-weight: bold;
    font-size: 15px;
  }
  .url {
    font-size: 18px;
  }
  .description {
    width: 100%;
  }
}
</style>
