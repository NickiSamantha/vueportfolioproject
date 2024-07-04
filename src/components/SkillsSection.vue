<template>
    <div class="skills-container  ">
      <div class="container mt-5 pt-5 ">
        <h2>SKILLS</h2>
        <div class="row mt-5">
          <h3>Technical Skills</h3>
        </div>
        <div class="row skills-row" v-if="skills?.length">
          <div v-for="(skill, index) in skills" :key="index" class="col-md-4 mb-4 col-sm-12 mb-5 pt-5">
            <div class="flip-card">
              <div class="flip-card-inner">
                <div class="flip-card-front">
                  <div class="skill-icon">
                    <img :src="skill.image" alt="Skill Icon">
                  </div>
                  <div class="skill-title">
                    <p>{{ skill.title }}</p>
                  </div>
                </div>
                <div class="flip-card-back">
                  <p>{{ skill.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <SpinnerComp v-else />
      </div>
  
      <div class="container pt-4">
        <div class="row mt-5 pt-5">
          <h3>Soft Skills</h3>
        </div>
        <div class="row skills-row" v-if="softskills?.length">
          <div v-for="(skill, index) in softskills" :key="index" class="col-md-4 col-sm-12 mb-4 pt-4">
            <div class="flip-card">
              <div class="flip-card-inner">
                <div class="flip-card-front">
                  <div class="skill-title">
                    <p>{{ skill.title }}</p>
                  </div>
                </div>
                <div class="flip-card-back">
                  <p>{{ skill.description }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <SpinnerComp v-else />
      </div>
    </div>
  </template>
  
  <script>
  import SpinnerComp from "@/components/Spinner.vue";
  
  export default {
    name: "SkillsComp",
    components: {
      SpinnerComp,
    },
    computed: {
      skills() {
        return this.$store.state.skills;
      },
      softskills() {
        return this.$store.state.softskills;
      },
    },
    created() {
      this.$store.dispatch("fetchSkills");
      this.$store.dispatch("fetchSoftskills");
    },
  };
  </script>
  
  <style scoped>
  .skills-container {
    margin-top: 20px;
    background-color: #d7f4f6;

  }
  
  .skills-row {
    justify-content: center;
  }
  
  .flip-card {
    background-color: #fce6d3;
    width: 100%;
    height: 250px;
    perspective: 1000px;
    margin-bottom: 20px;
  }
  
  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
  }
  
  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }
  
  .flip-card-front,
  .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    border: 1px solid black;
  }
  
  .flip-card-front {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  
  .flip-card-back {
    background-color: #fce6d3;
    color: #333;
    padding: 20px;
    transform: rotateY(180deg);
    text-align: center;
    align-content: center;
  }
  
  .skill-icon img {
    width: 80px; 
    height: 80px; 
    margin-bottom: 10px;
  }
  
  .skill-title p {
    font-weight: bold;
    font-size: 18px;
    margin-bottom: 5px;
  }
  
  @media (max-width: 768px) {
  .flip-card-inner {
    height: auto;
  }

  .flip-card-front,
  .flip-card-back {
    height: auto;
    padding: 10px;
    word-wrap: break-word;
    text-align: center;
    border: 1px solid black;
  }
  .skill-icon, 
  .skill-title {
    justify-content: center;
    align-items: center;
    margin-top: 10px;
  }

  /*remve this if it doesn't work */

  .flip-card {
    background-color: #fce6d3;
    width: 100%;
    height: 250px;
    perspective: 1000px;
    margin-bottom: 20px;
  }
  
  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
  }
  
  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }
  
  .flip-card-front,
  .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
  }
  
  .flip-card-front {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  
  .flip-card-back {
    background-color: #fce6d3;
    color: #0c0c0c;
    padding: 3px;
    transform: rotateY(180deg);
   
  }

}
  </style>
  