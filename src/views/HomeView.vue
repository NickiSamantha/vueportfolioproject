<template>
  <div class="container">
    <section class="row" id="landing">
      <LandingSection/>
    </section>
    <section class="row" id="about">
      <AboutSection/>
    </section>
    <section class="row" id="education">
      <EducationSection/>
    </section>
    <section class="row" id="skills">
      <SkillsSection/>
    </section>
    <section class="row" id=""></section>
    <section class="row" id=""></section>
 </div>
</template>

<script>
import LandingSection from '@/components/LandingSection.vue';
import AboutSection from '@/components/AboutSection.vue'
import EducationSection from '@/components/EducationSection.vue'
import SkillsSection from '@/components/SkillsSection.vue'
export default {
  name: 'HomeView',
  components: {
  LandingSection,
  AboutSection,
  EducationSection,
  SkillsSection

  }
}
</script>
