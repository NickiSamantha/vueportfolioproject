<template>
  <div class="wrapper">
    <NavBar></NavBar>
    <main class="container-fluid">
      <router-view />
    </main>
    <FooterComp></FooterComp>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue';
import FooterComp from '@/components/Footer.vue'
export default {
  components: {
    NavBar,
    FooterComp,
  },
};
</script>
<style></style>
