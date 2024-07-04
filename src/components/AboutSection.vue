<template>
    <div class="container mt-5 mb-5 pb-5">
      <div class="row align-content-center mt-5 pt-4">
        <h1 class="display-1" data-aos="fade-up" data-aos-anchor-placement="top-bottom">About</h1>
      </div>
      <div class="row align-items-center mt-5 pt-" v-if="about?.length">
        <div class="col-lg-6 col-12"  data-aos="fade-down"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000">
            <img src="https://nickisamantha.github.io/allImages/images/nickiaboutimg.jpg" alt="" class="img-fluid w-50 " loading="lazy">
       
        </div>
       <div class="col-lg-6 col-12 mt-4">
        <p v-for="(self, index) in about" :key="index"  
        data-aos="fade-down"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000">
          {{ self.title }}
        </p>
       </div>
      </div>
      <SpinnerComp v-else />
    </div>
  </template>
  
  <script>
  import AOS from 'aos';
  import 'aos/dist/aos.css';
  import SpinnerComp from "@/components/Spinner.vue";
  export default {
    name: "AboutComp",
  
    computed: {
      about() {
        return this.$store.state.about;
      },
    },
    created() {
      this.$store.dispatch("fetchAbout");
    },
    components: {
      SpinnerComp
    },
    mounted() {
    this.initAOS();
  },
  methods: {
    initAOS() {
      AOS.init({
        offset: 200,
        duration: 2000,
        easing: 'ease',
        anchorPlacement: 'bottom-top' 
      });
    }
  }
  };
  </script>
  
  <style scoped>

  </style>