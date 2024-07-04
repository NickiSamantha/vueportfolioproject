<template>
    <div class="container mt-5 pt-4">
        <div class="row mt-4">
     <h1 class="display-1" data-aos="fade-up" data-aos-anchor-placement="top-bottom">PROJECTS</h1>
        </div>
    <div class="row items pt-3 p-4 gap-4 col-12 " v-if="projects?.length">
     <CardComp v-for="(self, id) in projects" :key="id" class="p-2 card-hover" data-aos="fade-down"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000">
       
        <template #cardHeader>
          <p class="name-header"> {{ self.name }} </p>   
           <img
            class="img-fluid"
            :src="self.image"
            :alt="self.name"
            loading="lazy"
          />
        </template>
          <template #cardBody>
            <div class="description-container">
              <p class="description-text">{{ self.description }}</p>
            </div>
            
           <a :href="self.github" target="_blank" class="btn pink-border">
            <i class="fa-brands fa-github"></i>
          </a>
          <a :href="self.vercel" target="_blank" class="btn pink-border">
            View Project
          </a>
        </template>
     </CardComp>
   </div> 
   <SpinnerComp v-else /> 
 </div>
</template>

<script>
import SpinnerComp from "@/components/Spinner.vue";
import CardComp from "@/components/Card.vue";
import AOS from 'aos';
  import 'aos/dist/aos.css';
export default {
 name: "ProjectsComp",

 data(){
  return {
    loading:true,
  };
 },
 computed: {
   projects() {
     return this.$store.state.projects;
   },
 
 },
 created() {
   this.$store.dispatch("fetchProjects");
 },
 mounted() {
    this.initAOS();
  },
 methods: {
    async fetchProjects() {
      this.loading = true;
      await this.$store.dispatch("fetchProjects");
      this.loading = false;
    },
    initAOS() {
      AOS.init({
        offset: 200,
        duration: 2000,
        easing: 'ease',
        anchorPlacement: 'bottom-top' 
      });
    }
  },
 components: {
  SpinnerComp,
  CardComp
 }
};
</script>

<style  scoped>
@import 'aos/dist/aos.css';

.name-header {
  height: 30px;
  text-align: center;
  
}

.btn {
  margin: 5px;
  padding: 10px 20px;
  border: 1px solid #ff69b4;
  color: #ff69b4;
  background-color: transparent;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
}

.btn:hover {
  background-color: #ff69b4;
  color: white;
}

.description-container {
  height: 100px;
  overflow-y: auto;
}
.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 400px; 
  overflow: hidden;
  background-color: #f7e8ef;
}

.card-header img {
  width: 50%;
  height: auto;
}
.card-hover:hover {
  box-shadow: 1px 8px 8px rgba(0, 0, 0, 0.2);
  transition: box-shadow 0.1s ease-in-out;
}
</style>