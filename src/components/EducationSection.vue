<template>
    <div class="container mt-5">
      <div class="row mt-5">
        <h1 class="display-1">Resume</h1>
        <h2 class="mt-2">EDUCATION</h2>
      </div>
      <div class="row mt-5" v-if="education?.length">
        <div v-for="(self, id) in education" :key="id">
          <div class="border-resume lead m-auto p-2 mb-4 mt-4 shadow-lg ">
              <p> {{ self.year }} </p>   
              <p> {{ self.place }}</p>   
              <p> {{ self.courseName }}</p>   
              <p> {{ self.description }} </p>  
          </div>
        </div>
      </div>
      <SpinnerComp v-else />
    </div>
  </template>
  
  <script>
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
      SpinnerComp
    }
  };
  </script>
  
  <style  scoped>
  .border-resume{
      border:2px solid black;
      padding: 5px ;
      background: #CDEDDD;
      width: 65%;


  }
  .container {
    background-color: #d7f4f6;
  }
  </style>