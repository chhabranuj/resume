<template>
  <div class="certificates">
    <p class="title">CERTIFICATES</p>
    <div class="awards" v-for="item in data" :key="item.description">
      <div class="titleAndTime">
        <p class="projectName">
          {{ toUppercase(item.title) }}
        </p>
        <p class="time">{{ item.date }}</p>
      </div>
      <a class="url" :href="`${item.url}`" target="_blank">Certificate Link</a>
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
  name: "CertificatesLayout",
  props: ["certificates"],
  data() {
    return {
      data: {},
      toUppercase(value) {
        return value.toUpperCase();
      },
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.certificates));
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Akshar&display=swap");
.certificates {
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
  color: #71c6dd;
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
}
.time {
  color: #71c6dd;
  font-family: "Open Sans", sans-serif;
}
.url {
  font-family: "Open Sans", sans-serif;
  font-weight: bold;
  margin-top: 5px;
  color: rgba(255, 255, 255, 0.6);
}

.url:hover {
  color: #71c6dd;
}
.description {
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
  .certificates {
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
