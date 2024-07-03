<template>
  
    <div class="container-fluid mt-5 pt-5 Bg">
      
    <div class="row pt-3 p-4 gap-4 col-12" v-if="testimonials?.length">
      <h1>TESTIMONIALS</h1>
      <CardComp v-for="(self, index) in testimonials" :key="index" class="col-md-4 col-sm-12">
        <template #cardHeader>
          <img
            class="img-fluid"
            :src="self.profile"
            :alt="self.name"
            loading="lazy"
          />
        </template>
        <template #cardBody>
          <p>{{ self.name }} {{ self.surname }}</p>
          <p>{{ self.relation }}</p>
          <div class="quote-container">
            <p class="quote-text mb-4">{{ self.quote }}</p>
          </div>
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
    name: "TestimonialsComp",
  
    computed: {
      testimonials() {
        return this.$store.state.testimonials;
      },
    },
    created() {
      this.$store.dispatch("fetchTestimonials");
    },
    components: {
      SpinnerComp,
      CardComp,
    },
  };
  </script>
 
  
 <style scoped>

 



.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 550px; 
  overflow: hidden;
}

.card-header img {
  width: 100%;
  height: auto;
}

.quote-container {
  height: 200px;
  overflow-y: auto;
}

 </style>