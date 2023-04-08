<template>
  <b-row style="margin-left: 0; margin-right: 0">
    <b-col md="4">
      <b-img :src="avatar" id="avatar-img" alt="Muhammad Irsyad Aliyahya" />
    </b-col>
    <b-col md="8">
      <h2 class="intro animate__animated animate__fadeInUp animate__fast">
        Hi 👋,
        <br />I<span>'m Muhammad Irsyad Aliyahya</span>.
      </h2>
      <div class="col-md-10 info">
        A <b>student</b> and <b>website development enthusiast</b> passionate
        about solving problems with tech.<br />
        I am skilled with building beautiful <b>websites</b> and currently i'm
        exploring <b>vuejs</b>.
        <br />
        <b-button
          class="action-btn animate__animated animate__wobble animate__delay-4s animate__fast"
          to="/projects"
        >
          Explore >
        </b-button>
        <b-button class="action-btn" to="/contact" variant="primary">
          Get In Touch
        </b-button>
        <!-- .SOCIAL LINKS SECTION -->
        <div
          class="social-icons animate__animated animate__fadeInUp animate__delay-1s"
        >
          <social-link :to="socialLinks.github">
            <GithubIcon/>
          </social-link>

          <social-link :to="socialLinks.linkedin">
            <LinkedinIcon/>
          </social-link>

          <social-link :to="socialLinks.mail">
            <MailIcon/>
          </social-link>
        </div>
      </div>
    </b-col>
  </b-row>
</template>

<script>
// import icon
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import LinkedinIcon from "vue-ionicons/dist/logo-linkedin.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";
// export icon
export default {
  components: {
    GithubIcon,
    LinkedinIcon,
    MailIcon,
  },

  data() {
    return {
      avatar: require("@/assets/about.jpg"),
      // Sosial Link
      socialLinks: {
        github: "https://github.com/IRS-dev",
        linkedin:"https://www.linkedin.com/in/muhammad-irsyad-aliyahya-698049222/",
        mail: "mailto:irsyadalyahya5@gmail.com",
      },
    };
  },

  head: {
    title: "Portofolio ⚡ - Muhammad Irsyad Aliyahya",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          " A student and website development enthusiast passionate about solving problems with tech I am skilled with building beautiful websites and currently i'm exploring vuejs.",
      },
    ],
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();

      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });
  },
};
</script>
