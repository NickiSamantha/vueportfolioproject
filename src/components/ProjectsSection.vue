<template>
    <div class="container mt-5 pt-4">
   <div class="row mt-4">
     <h1 class="display-1">PROJECTS</h1>
   </div>
   <div class="row items" v-if="projects?.length">
     <CardComp v-for="(self, id) in projects" :key="id">
       
        <template #cardHeader>
          <p> {{ self.name }} </p>   
           <img
            class="img-fluid w-25"
            :src="self.image"
            :alt="self.name"
            loading="lazy"
          />
        </template>
          <template #cardBody>
            <p>{{ self.description }}</p>
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
export default {
 name: "ProjectsComp",

 computed: {
   projects() {
     return this.$store.state.projects;
   },
 
 },
 created() {
   this.$store.dispatch("fetchProjects");
 },
 components: {
  SpinnerComp,
  CardComp
 }
};
</script>

<style  scoped>



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


</style>