<template>
  <div class="about page animate__animated animate__fadeIn">
    <h2>Recent Project</h2>
    <div class="container">
      <div class="row" v-for="(project, index) in projects" :key="index">
        <div class="col-md-5">
          <img
            :src="project.image_cover"
            :alt="project.title"
            class="project-cover"
          />
        </div>
        <div class="col-md-5">
          <h2 class="mt-3" style="text-align: left">
            {{ project.title }}
            <hr class="dope" />
          </h2>
          <b-card class="mt-3 mb-3 text-left text-dark">
            <p>{{ project.description }}</p>
            <b-link :href="project.github_url"
            >View source code <GithubIcon style="color: #000"
          /></b-link>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import LinkIcon from "vue-ionicons/dist/md-link.vue";
import GithubIcon from "vue-ionicons/dist/logo-github.vue";

export default {
  components: {
    GithubIcon,
    LinkIcon,
  },
  data() {
    return {
      projects: [
        {
          title: "Laravel Blog",
          tag: "Progressive Web App",
          description:
            "Simple blog using laravel. implement CRUD and clean code",
          image_cover: require("@/assets/speak.jpg"),
          github_url: "https://github.com/IRS-dev/laravel-Blog-005",
        },
        {
          title: "Laravel Lumen REST API",
          tag: "Progressive Web App",
          description:
            "lumen simple REST API (CRUD)",
          image_cover: require("@/assets/illustration.jpg"),
          github_url: "https://github.com/IRS-dev/lumen-rest-api",
        },
        {
          title: "Laravel Scrap Movie Data",
          tag: "Progressive Web App",
          description:
            "Scrapping data from movie website",
          image_cover: require("@/assets/qr-1.png"),
          github_url: "https://github.com/IRS-dev/laravel-scrap-movie",
        },
        {
          title: "Vue fetch API",
          tag: "Progressive Web App",
          description:
            "Scrapping data from movie website",
          image_cover: require("@/assets/qr-1.png"),
          github_url: "https://github.com/IRS-dev/vue-fetch-api",
        },
      ],
    };
  },
  methods: {
    isEven(n) {
      if (n % 2 == 0) {
        return true;
      } else {
        return false;
      }
    },
  },
  head: {
    title: "Recent Projects 💻 - Muhammad Irsyad Aliyahya ",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "View all the recents open-sourced projects built with ♥ by Asaolu Elijah, open-sourced means this project source code are publicly available for everyone to use or modify.",
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Recent Projects 💻 - Muhammad Irsyad Aliyahya",
      },
      {
        property: "og:description",
        content:
          "View all the recents open-sourced projects built with ♥ by Asaolu Elijah, open-sourced means this project source code are publicly available for everyone to use or modify.",
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/man-computer.png"),
      },
    ],
  },
};
</script>
<style scoped>
.row {
  margin-top: 70px;
}
.project-cover {
  width: inherit;
  border-radius: 3px;
}
hr.dope {
  border: 0;
  width: 90px;
  border-top: 2px solid #dc3545;
  text-align: left;
  margin: initial;
  margin-top: 7px;
  margin-left: 5px;
}
</style>
