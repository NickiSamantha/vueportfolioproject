<!-- <template>
  <div class="container-fluid mt-5 pt-5 Bg">
    <div class="row pt-3 p-2 gap-4 " v-if="testimonials?.length">
      <h1 data-aos="fade-up" data-aos-anchor-placement="top-bottom">
        TESTIMONIALS
      </h1>
      <CardComp
        v-for="(self, index) in testimonials"
        :key="index"
        class="col-md-4 col-sm-12 2p-2 card"
        data-aos="fade-down"
        data-aos-anchor-placement="top-bottom"
        data-aos-delay="index * 1000"
      >
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
import AOS from "aos";
import "aos/dist/aos.css";
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
  mounted() {
    this.initAOS();
  },
  methods: {
    initAOS() {
      AOS.init({
        offset: 200,
        duration: 2000,
        easing: "ease",
        anchorPlacement: "bottom-top",
      });
    },
  },
};
</script>

<style scoped>
@import "aos/dist/aos.css";
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
  background-color: #f7e8ef;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card-header img {
  width: 100%;
  height: auto;
}

.quote-container {
  height: 200px;
  overflow-y: auto;
}

/* Hover effect */
.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
  background-color: #f1bed5;
}
</style> -->
