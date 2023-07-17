<template>
  <div class="volunteerings">
    <p class="title">VOLUNTEERINGS</p>
    <div class="awards" v-for="item in data" :key="item.description">
      <div class="titleAndTime">
        <p class="projectName">
          {{ toUppercase(item.title) }}
        </p>
        <p class="time">
          {{ item.startDate }} -
          <span style="color: #71c6dd">{{ item.endDate }}</span>
        </p>
      </div>
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
  name: "VolunteeringLayout",
  props: ["volunteerings"],
  data() {
    return {
      data: {},
      toUppercase(value) {
        return value.toUpperCase();
      },
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.volunteerings));
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Akshar&display=swap");
.volunteerings {
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
.description {
  width: 75%;
  color: white;
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
  .volunteerings {
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
    width: 100%;
  }
}
</style>
