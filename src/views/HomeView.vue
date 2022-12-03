
<template>
  <div class="home">
     <CarouselTop class="carouseltop" v-slot="{currentSlide}">
        <SliderTop v-for="(slide, index) in carouselSlides" :key="index">
          <div v-show="currentSlide === index + 1" class="slides-info">
            <img :src="require(`../assets/${slide}.jpg`)" alt="" >
        </div>
           
        </SliderTop>        
     </CarouselTop>
  </div>
</template>

<script>
import CarouselTop from "../components/CarouselTop.vue";
import SliderTop from "../components/SliderTop.vue";

export default {
  name: "HomeView",
  components: { CarouselTop, SliderTop },
  setup () {

    const carouselSlides = ["bg1", "bg2", "bg3"];
    return {carouselSlides}


  },
};
</script>

<style lang="scss" scoped>

.carouseltop {

  position: relative;
  max-height: 100vh;
  height: 100vh;

  .slides-info {

    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    max-height: 100%;
    height: 100%;


    img {

      min-width: 100%;
      height: 100%;
      object-fit: cover;


    }

  }

}

</style>