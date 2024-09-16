<template>
  <div class="container">
    <section class="row" id="landing">
      <LandingSection />
    </section>
    <section class="row" id="about">
      <AboutSection />
    </section>
    <section class="row" id="education">
      <EducationSection />
    </section>
    <section class="row" id="skills">
      <SkillsSection />
    </section>
    <section class="row" id="experience">
      <ExperienceSection />
    </section>
    <section class="row" id="testimonials">
      <TestimonialsSection />
    </section>
    <section class="row" id="projects">
      <ProjectsSection />
    </section>
    <section class="row" id="reachMe">
      <ContactSection />
    </section>
  </div>
</template>

<script>
import LandingSection from "@/components/LandingSection.vue";
import AboutSection from "@/components/AboutSection.vue";
import EducationSection from "@/components/EducationSection.vue";
import SkillsSection from "@/components/SkillsSection.vue";
import ExperienceSection from "@/components/ExperienceSection.vue";
import ProjectsSection from "@/components/ProjectsSection.vue";
import TestimonialsSection from "@/components/TestimonialsSection.vue";
import ContactSection from "@/components/ContactSection.vue";
export default {
  name: "HomeView",
  components: {
    LandingSection,
    AboutSection,
    EducationSection,
    SkillsSection,
    ExperienceSection,
    TestimonialsSection,
    ProjectsSection,
    ContactSection,
  },
};
</script>
