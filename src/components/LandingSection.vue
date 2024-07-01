<template>
    <div class="container-fluid mt-5">
      <div class="row vh-100 align-items-center">
        <div class="col mt-5">
          <img
            src="https://nickisamantha.github.io/allImages/images/Nicki.jpg"
            alt="profile"
            class="img-fluid"
            loading="lazy"
          />
        </div>
        <div class="col">
          <div id="details">
            <h1 class="display-1">NICKI ABELS</h1>
            <p v-if="jobTitle ">
              I am an aspiring 
              <span>{{ title }} </span>
              <span class="d-block">{{ jobTitle[0]?.personalStatement }}</span>
            </p>
           <Spinner v-else/>
          </div>

        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import Spinner from './Spinner.vue'
  import { computed, onMounted, ref } from "vue";
  import { useStore } from "vuex";
  const store = useStore();
  const jobTitle = computed(() => store.state.jobTitle);
  const title = ref("Web Developer");
  const cnt = ref(-1);
  
  function repeat() {
    try {
      if (cnt.value == jobTitle.value?.length) cnt.value = 0;
      title.value = jobTitle.value?.at(cnt.value)?.title;
      setTimeout(repeat, 2000);
      cnt.value++;
    } catch (e) {
      //
    }
  }
  onMounted(() => {
    store.dispatch("fetchJobTitle");
    repeat();
  });
  </script>
  
  <style scoped>
  
  </style>