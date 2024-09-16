<template>
  <div class="container mt-5">
    <div
      class="row mt-5"
      data-aos="fade-up"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000"
    >
      <h1 class="display-1">Resume</h1>
      <h2 class="mt-2">EDUCATION</h2>
    </div>
    <div class="row mt-5" v-if="education?.length">
      <div
        v-for="(self, id) in education"
        :key="id"
        data-aos="fade-down"
        data-aos-anchor-placement="top-bottom"
        data-aos-delay="index * 1000"
      >
        <div class="border-resume lead m-auto p-2 mb-4 mt-4 shadow-lg">
          <p>{{ self.year }}</p>
          <p>{{ self.place }}</p>
          <p>{{ self.courseName }}</p>
          <p>{{ self.description }}</p>
        </div>
      </div>
    </div>
    <SpinnerComp v-else />
  </div>
</template>

<script>
import AOS from "aos";
import "aos/dist/aos.css";
import SpinnerComp from "@/components/Spinner.vue";
export default {
  name: "EducationComp",

  computed: {
    education() {
      return this.$store.state.education;
    },
  },
  created() {
    this.$store.dispatch("fetchEducation");
  },
  components: {
    SpinnerComp,
  },
  mounted() {
    this.initAOS();
  },
  methods: {
    initAOS() {
      AOS.init({
        offset: 200,
        duration: 2000,
        easing: "ease",
        anchorPlacement: "bottom-top",
      });
    },
  },
};
</script>

<style scoped>
.border-resume {
  border: 2px solid black;
  padding: 2px;
  background: #cdeddd;
  width: 70%;
}
.container {
  background-color: #d7f4f6;
}
</style>
