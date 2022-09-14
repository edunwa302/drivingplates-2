<template>
  <section class="pb-28">
    <!-- <Carousel :autoplay="2000" :wrap-around="true" :settings="settings">
      <Slide v-for="n in 25" :key="n">
        <div class="carousel_item h-full">
          <img class="h-full" :src="`/images/slide${n}.jpg`" loading='lazy'/>
        </div>
      </Slide>
      <template #addons>
        <Navigation />
      </template>
    </Carousel> -->
    <VueSlickCarousel v-bind="settings">
      <img v-for="n in 25" :key="n" :src="`/images/slide${n}.jpg`" :alt="`slide${n}`" /> 
     
    </VueSlickCarousel>
  </section>
</template> 
<script>
// import { Carousel, Slide, Navigation } from "vue3-carousel";
// import "vue3-carousel/dist/carousel.css";
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
  // optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
  name: "slider",
  components: {
    VueSlickCarousel,
    // Carousel,
    // Slide,
    // Navigation,
  },
  data() {
    return {
      settings: {
        accessibility: true,
        autoplay: true,
        centerMode: true,
        dots: false,
        slidesToScroll: 1,
        speed: 300,
        infinite: true,
        slidesToShow: 5,
        arrows: true,
      },
    };
  },
};
</script>
<style>
  slick-next
.slick-arrow {
    background: rgba(0,0,0,.1);
    padding: 1rem 0;
    font-size: calc(2rem, 3rem + 5vw, 2rem + 7vw);
    border-radius: unset;
    right: 1rem;
    transition: background .3s ease;
}

.slick-next:hover, .slick-prev:hover{
    background: rgba(0,0,0,.3);
}
.slick-prev{
    left: 1rem;
    right: 0;
}
</style>
