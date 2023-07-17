<template>
  <div class="aboutMe">
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
    />
    <p class="title">
      {{ toUppercase(data.firstName) }}
      <span style="color: #71c6dd">{{ toUppercase(data.lastName) }}</span>
    </p>
    <div class="personalInfo">
      <span style="color: #71c6dd">{{ toUppercase(data.address) }}</span>
      <span style="color: #8b8b8b"> ~ </span>
      <span>{{ toUppercase(data.state) }}</span>
      <span style="color: #8b8b8b"> ~ </span>
      <span style="color: #71c6dd">{{ toUppercase(data.country) }}</span>
      <span style="color: #8b8b8b"> ~ </span>
      <a
        :href="`${data.whatsapp}`"
        target="_blank"
        style="color: white; text-decoration: none"
        >{{ data.phoneNumber }}</a
      >
      <span style="color: #8b8b8b"> ~ </span>
      <a
        :href="`${data.mail}`"
        target="_blank"
        style="color: #71c6dd; text-decoration: none"
        >{{ toUppercase(data.email) }}</a
      >
    </div>
    <p class="about">{{ data.about }}</p>
    <div class="externalLinks">
      <a :href="`${data.github}`" target="_blank"
        ><md-icon class="fa fa-github link"></md-icon
      ></a>
      <a :href="`${data.linkedin}`" target="_blank"
        ><md-icon class="fa fa-linkedin link" style="color: #71c6dd"></md-icon
      ></a>
      <a :href="`${data.mail}`" target="_blank"
        ><md-icon class="fa fa-envelope link"></md-icon
      ></a>
      <a :href="`${data.whatsapp}`" target="_blank"
        ><md-icon class="fa fa-whatsapp link" style="color: #71c6dd"></md-icon
      ></a>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutMeLayout",
  props: ["about"],
  data() {
    return {
      data: {},
      toUppercase(value) {
        return value.toUpperCase();
      },
    };
  },
  beforeMount() {
    this.data = JSON.parse(JSON.stringify(this.about));
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap");
a:hover {
  text-decoration: underline !important;
}
.aboutMe {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;
  min-height: 100vh;
  margin: 0 5%;
  color: white;
}
.title {
  font-family: "Poppins", sans-serif;
  font-size: 80px;
  margin: 0;
}
.personalInfo {
  font-family: "Poppins", sans-serif;
  margin: 0;
  font-size: medium;
}
.about {
  font-family: "Open Sans", sans-serif;
  white-space: pre-line;
  font-size: medium;
  letter-spacing: 1px;
  line-height: 1.5;
  text-align: justify;
  margin: 50px 0;
  font-weight: 300;
}
.externalLinks {
  display: flex;
}
.link {
  margin: 0 20px;
  font-size: 40px;
  cursor: pointer;
  color: white;
}

@media screen and (max-width: 900px) {
  .aboutMe {
    padding: 25% 0;
    min-height: auto;
  }
  .title {
    font-size: 60px;
  }
  .personalInfo {
    font-size: 15px;
  }
  .about {
    margin: 30px 0;
  }
}
</style>
