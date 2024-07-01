<template>
    <div class="container mt-5 mb-5 pb-5">
      <div class="row align-content-center mt-5">
        <h1 class="display-1">About</h1>
      </div>
      <div class="row align-items-center mt-5" v-if="about?.length">
        <div class="col-lg-6 col-12">
            <img src="https://nickisamantha.github.io/allImages/images/nickiaboutimg.jpg" alt="" class="img-fluid w-50 " loading="lazy">
       
        </div>
       <div class="col-lg-6 col-12 mt-4">
        <p v-for="(self, index) in about" :key="index">
          {{ self.title }}
        </p>
       </div>
      </div>
      <SpinnerComp v-else />
    </div>
  </template>
  
  <script>
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
    }
  };
  </script>
  
  <style scoped>
   
  </style>