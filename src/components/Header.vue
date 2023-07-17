<template>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
  />
  <div class="headerParent">
    <div class="header">
      <img src="./../assets/anuj.png" class="image" />
      <div class="contentParent">
        <p
          v-for="item in content"
          :key="item"
          @click="getItemName(item)"
          v-bind:class="getClass(item)"
        >
          {{ item }}
        </p>
      </div>
    </div>
    <a href="/AnujChhabra_Resume.pdf" target="_blank" class="downloadResume">
      <md-icon
        class="fa fa-link"
        style="color: #71c6dd; margin-right: 10px"
      ></md-icon>
      <p>
        View <span style="color: #71c6dd">Resume </span
        ><span style="font-size: x-small">(pdf)</span>
      </p>
    </a>
  </div>

  <!-- Media View -->
  <div class="mediaHeader">
    <div class="mediaTitleAndMenu">
      <p class="title">
        <span style="color: #71c6dd">{{ firstName }}</span> {{ lastName }}
      </p>
      <md-icon class="fa fa-bars menu" @click="toggleMenu()"></md-icon>
    </div>
    <transition name="fade">
      <div class="mediaContents" v-if="menuIsOpen">
        <hr class="divider" />
        <ul class="conentList">
          <li
            class="mediaContent contents"
            v-for="item in content"
            :key="item"
            @click="getItemName(item)"
            v-bind:class="getClass(item)"
          >
            {{ item }}
          </li>
        </ul>
        <a
          href="/src/assets/AnujChhabra_Resume.pdf"
          target="_blank"
          class="downloadResume"
        >
          <md-icon
            class="fa fa-link"
            style="color: #71c6dd; margin-right: 10px"
          ></md-icon>
          <p>
            View <span style="color: #71c6dd">Resume </span
            ><span style="font-size: x-small">(pdf)</span>
          </p>
        </a>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "HeaderLayout",
  data() {
    return {
      clicked: "ABOUT ME",
      firstName: "Anuj",
      lastName: "Chhabra",
      content: [
        "ABOUT ME",
        "PROFESSIONAL \n EXPERIENCE",
        "EDUCATION",
        "SKILLS",
        "PROJECTS",
        "CERTIFICATES",
        "VOLUTEERINGS",
      ],
      menuIsOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuIsOpen = !this.menuIsOpen;
    },
    getItemName(value) {
      this.$emit("clicked", value);
      this.clicked = value;
      this.menuIsOpen = false;
    },
    getClass(value) {
      if (value == this.clicked) {
        return "mediaContent content whiteTitle";
      } else {
        return "mediaContent content";
      }
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Fira+Sans:wght@600&display=swap");
.mediaHeader {
  display: none;
}

.headerParent {
  height: 100vh;
  width: 325px;
  background-color: #51546e;
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-direction: column;
}

.header {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.image {
  width: 50%;
  height: 28%;
  border-radius: 50%;
  border: 10px solid #64657d;
  margin-bottom: 25px;
  object-fit: contain;
  background-color: #3f4156;
}

.contentParent {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.content {
  color: rgba(255, 255, 255, 0.5);
  font-family: "Fira Sans", sans-serif;
  text-align: center;
  letter-spacing: 1.5px;
  cursor: pointer;
  white-space: pre-line;
  margin: 12px 0;
}
.contents:hover {
  color: white;
}
.whiteTitle {
  color: white;
}
.downloadResume {
  color: white;
  text-decoration: none;
  width: 80%;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 10px;
  font-family: "Fira Sans", sans-serif;
  border: 2px solid rgba(255, 255, 255, 0.1);
}

.downloadResume:hover {
  border: 2px solid #71c6dd;
  background-color: #3f4156;
}
@media screen and (max-width: 900px) {
  .headerParent {
    display: none;
  }
  .mediaHeader {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    padding: 0 4%;
    color: white;
    background-color: #51546e;
    top: 0;
    z-index: 1000;
    position: fixed;
    width: 92%;
  }
  .mediaTitleAndMenu {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    height: 10vh;
  }
  .title {
    font-family: "Poppins", sans-serif;
    font-size: 25px;
    margin: 15px 0;
  }
  .menu {
    padding: 5px 10px;
    border: 1.5px solid rgba(255, 255, 255, 0.1);
    border-radius: 5px;
    font-size: 20px;
    cursor: pointer;
  }
  .mediaContents {
    width: 100%;
    height: 92vh;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: flex-start;
  }

  .conentList {
    width: calc(100% - 20px);
    margin-left: 20px;
  }
  .mediaContent {
    text-align: start;
    margin: 20px 0;
  }
  .divider {
    border: 0;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    width: 100%;
    margin: 0;
  }
  .fade-enter {
  }
  .fade-enter-active {
    animation: fade-in 1s;
  }
  .fade-leave {
  }
  .fade-leave-active {
    animation: fade-out 0.5s;
  }
  @keyframes fade-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  @keyframes fade-out {
    from {
      opacity: 1;
    }
    to {
      opacity: 0;
    }
  }
  .downloadResume {
    margin-top: 40px;
  }
}
</style>
