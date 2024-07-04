<template>
    <div class="container align-items-center pt-5 pb-4">
    <div class="row mt-5 pt-3" data-aos="fade-up"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000">
      <h2>Experience</h2>
    </div>
    <div class="row" v-if="experience?.length" >
      <div v-for="(self, id) in experience" :key="id" data-aos="fade-down"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000">
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
 import AOS from 'aos';
 import 'aos/dist/aos.css';
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
.border-resume{
    border:2px solid black;
    padding: 5px ;
    background: #CDEDDD;  
}
.container {
  background-color: #d7f4f6;
}
</style>