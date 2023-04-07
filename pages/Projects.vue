<template>
  <div class="about page animate__animated animate__fadeIn">
    <h2>Recent Project</h2>
    <div class="container">
      <div class="row" v-for="(data, index) in project" :key="index">
        <div class="col-md-5">
          <img :src="data.image_cover" class="project-cover" />
        </div>
        <div class="col-md-5">
          <h2 class="mt-3" style="text-align: left">
            {{ data.title }}
            <hr class="dope" />
          </h2>
          <b-card class="mt-3 mb-3 text-left text-dark">
            <p>{{ data.description }}</p>
            <b-link :href="data.github_url"
              >View source code <GithubIcon style="color: #000"
            /></b-link>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
// import icon
import LinkIcon from "vue-ionicons/dist/md-link.vue";
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import axios from "axios";

// export component icon
export default {
  components: {
    GithubIcon,
    LinkIcon,
  },
  data() {
    return {
      laravel: require("@/assets/laravel.jpg"),
      vue: require("@/assets/vue.png"),
      project: null,
    };
  },
  // fetch data from json
  async fetch() {
    const { data } = await axios.get(
      "https://intern-fullstack-gamatechno.vercel.app/data/project.json"
    );
    this.project = data.data;
    console.log(this.project);
  },
  head: {
    title: "Recent Projects 💻 - Muhammad Irsyad Aliyahya ",
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
