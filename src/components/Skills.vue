<template>
  <div class="skills">
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
    />
    <p class="title">SKILLS</p>
    <p class="subTitle">
      <span style="color: #71c6dd">DESIGN</span> TECHNOLOGIES
      <span style="color: #71c6dd">&</span> TOOLS
    </p>
    <div class="technologies">
      <p
        class="technology"
        v-for="(item, index) in data.technologies"
        :key="item"
      >
        {{ item }}
        <span
          v-if="index != data.technologies.length - 1"
          style="color: #71c6dd"
          >~</span
        >&nbsp;
      </p>
    </div>
    <p class="subTitle">WORK<span style="color: #71c6dd">FLOW</span></p>
    <div class="workflowParent">
      <div class="workflow" v-for="item in data.workflow" :key="item">
        <span style="color: #71c6dd"
          ><md-icon class="fa fa-check checkSign"></md-icon
        ></span>
        <p class="workflowDetails">{{ item }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SkillsLayout",
  props: ["skills"],
  data() {
    return {
      data: {},
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.skills));
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Akshar&display=swap");
.skills {
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
  margin: 0 0 5px 0;
  color: #71c6dd;
}
.subTitle {
  font-family: "Poppins", sans-serif;
  font-size: 30px;
  margin: 30px 0 15px 0;
}
.technologies {
  display: flex;
  flex-wrap: wrap;
}
.technology {
  font-size: 45px;
  font-family: "Open Sans", sans-serif;
  margin: 5px 0;
}
.workflowParent {
  display: flex;
  align-items: flex-start;
  flex-direction: column;
}
.workflow {
  display: flex;
  justify-content: center;
  align-items: center;
}
.checkSign {
  font-size: 20px;
  margin-right: 10px;
}
.workflowDetails {
  font-family: "Akshar", sans-serif;
  font-weight: 300;
  font-size: 18px;
  margin: 5px 0;
  letter-spacing: 0.5px;
}
@media screen and (max-width: 900px) {
  .skills {
    padding: 25% 0;
    min-height: auto;
  }
  .title {
    font-size: 35px;
    margin: 0 0 15px 0;
  }
  .subTitle {
    font-size: 22px;
    margin: 20px 0 15px 0;
  }
  .technology {
    font-size: 20px;
  }
}
</style>
