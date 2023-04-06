<template>
  <b-container class="page animate__animated animate__fadeIn">
    <b-row class="justify-content-center">
      <b-col cols="md-6">
        <h2>Get in touch 💌</h2>

        <p class="text-left">
          If you have any question or just want to say hi, i'll try my best to
          get back to you.
        </p>
        <!-- alert if success -->
        <b-alert show variant="success" v-if="showAlert">
          <strong>All done 🎉</strong><br />
          Thanks for reaching out {{ this.formData.name }}, I'll reply as soon
          as i can.
        </b-alert>
        <!--form data  -->
        <b-form class="mb-5" @submit.prevent="sendMessage">
          <b-form-group id="input-group-1" label="Your Name:">
            <b-form-input
              placeholder="Your name"
              v-model="formData.name"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-2" label="Your Email:">
            <b-form-input
              v-model="formData.email"
              type="email"
              placeholder="yourmail@gmail.com"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-3" label="Your Message">
            <b-form-textarea
              v-model="formData.message"
              no-resize
              rows="3"
              placeholder="Watsup Irsyad, are you available for.."
              required
            ></b-form-textarea>
          </b-form-group>

          <b-button type="submit" variant="primary">Submit</b-button>
        </b-form>
      </b-col>
    </b-row>
  </b-container>
</template>
<script>
export default {
  data() {
    return {
      showAlert: false,
      formData: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    async sendMessage(e) {
      const self = this;
      var data = new FormData();

      data.append("Name", self.formData.name);
      data.append("Email", self.formData.email);
      data.append("Message", self.formData.message);

      fetch("https://formspree.io/f/myyanonj", {
        method: "POST",
        body: data,
        headers: {
          Accept: "application/json",
        },
      }).then((response) => {
        if (response.ok) {
          this.showAlert = true;
          form.reset();
        } else {
          alert("Sending message failed, please try again");
        }
      });
    },
  },
  head: {
    title: "Contact 📧 - Muhammad Irsyad Aliyahya",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Do you have any enquires? Send a message now to Muhammad Irsyad Aliyahya",
      },
    ],
  },
};
</script>
<style scoped>
.container {
  margin-top: 120px;
}
form {
  margin-top: 40px;
  text-align: left;
}
</style>
