<template>
  <div class="container mt-2">
    <div class="row vh-100 align-items-center landing flex-md-row">
      <div
        class="col-md-6 mt-5 order-1 order-md-1"
        data-aos="fade-left"
        data-aos-anchor-placement="top-bottom"
        data-aos-delay="index * 1000"
      >
        <img
          src="https://nickisamantha.github.io/allImages/images/Nicki.jpg"
          alt="profile"
          class="img-fluid landpic"
          loading="lazy"
        />
      </div>
      <div
        class="col-md-6 order-2 order-md-2"
        data-aos="fade-right"
        data-aos-anchor-placement="top-bottom"
        data-aos-delay="index * 1000"
      >
        <div id="details" class="titleLand">
          <h1 class="display-1">NICKI ABELS</h1>
          <p v-if="jobTitle">
            I am an aspiring
            <span>{{ title }} </span>
          </p>
          <Spinner v-else />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Spinner from "./Spinner.vue";
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
    setTimeout(repeat, 1000);
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

<style scoped></style>
