<template>
    <div class="container align-items-center mt-5">
    <div class="row mt-5 pt-3">
      <h2>Experience</h2>
    </div>
    <div class="row" v-if="experience?.length">
      <div v-for="(self, id) in experience" :key="id">
        <div class="border-resume lead  m-4 shadow-lg">
            <p> {{ self.duration }} </p>   
            <p> {{ self.jobTitle }}</p>   
            <p> {{ self.companyName }}</p>   
            <p> {{ self.duties }} </p>  
        </div>
      </div>
    </div>
    <SpinnerComp v-else />
  </div>

</template>

<script>
    import SpinnerComp from "@/components/Spinner.vue";
export default {
  name: "ExperienceComp",

  computed: {
    experience() {
      return this.$store.state.experience;
    },
  
  },
  created() {
    this.$store.dispatch("fetchExperience");
  },
  components: {
    SpinnerComp
  }
};
</script>

<style scoped>
.border-resume{
    border:2px solid pink;
    padding: 5px ;
    background: #CDEDDD;  
}
.container {
    background-color: #C0E9ED;
}

</style>