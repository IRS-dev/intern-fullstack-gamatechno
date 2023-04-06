<template>
  <div class="container animate__animated animate__fadeIn">
    <div class="row">
      <div class="col-md-6">
        <div class="about">
          <h1 class="line-after">About Me</h1>
          <h4 class="mt-4">Hey 👋</h4>
          <p>
            My name is Muhammad Irsyad Aliyahya, I am a <b>student</b> and
            <b>website development enthusiast</b>. Currently studying vuejs and
            laravel.
          </p>
          <p>
            I have <b>{{ currYear - startYear }}+ years experience</b> in
            crafting beautiful web. I like to learn new things everyday
          </p>
          <h4 class="mt-5">Tech Stacks</h4>
          <p>Below are some of the technologies I use daily:</p>
            <TechStack/>
          <h4 class="mt-5">Education</h4>
          <Education/>
        </div>
      </div>
      <div class="col-md-6">
        <img
          src="@/assets/person.jpeg"
          alt="person"
          class="abt-img"
        />
      </div>
    </div>
  </div>
</template>
<script>
// import component
import TechStack from '../components/TechStack.vue';
import Education from '../components/Education.vue';
// export component
export default {
  components: {
      TechStack,
      Education
  },
  // data 
  data() {
    return {
      startYear: 2021,
      currYear: new Date().getFullYear(),
    };
  },
  head: {
    title: "About 🕵️‍♂️ - Muhammad Irsyad Aliyahya",
    meta: [
      {
        hid: "description",
        name: "description",
        // currYear - startYear
        content: `Hey there 👋 My name is Muhammad irsyad Aliyahya,, I am a student and website development enthusiast. Currently studying vuejs and laravel.`,
      },
    ],
  },
};
</script>
<style scoped>
.container {
  margin-top: 140px;
  text-align: left;
}
.line-after {
  overflow: hidden;
}
.line-after::after {
  content: "";
  display: inline-block;
  height: 0.5em;
  vertical-align: bottom;
  width: 100%;
  margin-right: -100%;
  margin-left: 10px;
  border-top: 2px solid rgb(211, 46, 46);
}
.abt-img {
  width: inherit;
  height: inherit;
  border-radius: 5px;
}
/* .abt-img:hover {
  animation: swing;
  animation-duration: 2s;
} */
</style>
