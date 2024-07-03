<template>
    <div class="container mt-5">
      <div class="row vh-100 align-items-center">
        <div class="col mt-5">
          <transition name="hop">
            <img
            src="https://nickisamantha.github.io/allImages/images/Nicki.jpg"
            alt="profile"
            class="img-fluid"
            loading="lazy"
            v-show="imageVisible"
          />
          </transition>
         
        </div>
        <div class="col">
          <transition name="hop">
            <div id="details" v-show="detailsVisible">
            <h1 class="display-1 ">NICKI ABELS</h1>
            <p v-if="jobTitle ">
              I am an aspiring 
              <span>{{ title }} </span>
              <!-- <span class="d-block">{{ jobTitle[0]?.personalStatement }}</span> -->
            </p>
           <Spinner v-else/>
          </div>
          </transition>
          

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
  
  const imageVisible = ref(false);
  const detailsVisible = ref(false);

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
    //hop js
    setTimeout(() => {
    imageVisible.value = true;
    detailsVisible.value = true;
  }, 2000);
  });
  </script>
  
  <style scoped>
  @keyframes hop {
  0% {
    transform: translateY(-100%);
    opacity: 0;
  }
  50% {
    transform: translateY(0%);
    opacity: 1;
  }
  70% {
    transform: translateY(-10%);
  }
  100% {
    transform: translateY(0%);
  }
}

.hop-enter-active,
.hop-leave-active {
  transition: all 2s ease;
}

.hop-enter-from,
.hop-leave-to {
  opacity: 0 ;
  transform: translateY(-100%);
}

img, #details {
  animation: hop 2s ease-in-out;
}
  
  </style>