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
  mounted() {
    let sliderArrows = document.querySelectorAll(".slick-arrow");
    sliderArrows.forEach(arrow => arrow.innerHTML = "");
  },
};
</script>
<style>
button.slick-arrow{
  width: 2.5rem;
  height: 2.5rem;
  background-color: rgba(0,0,0,.2);
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  color: unset;
  z-index: 5;
  cursor: pointer;
  transition: .3s ease;
}
button.slick-arrow:hover, button.slick-arrow:focus{
  background-color: rgba(0,0,0,.4);
  color: unset; 
}
.slick-next{
  right: 0;
}
.slick-prev{
  left: 0;
}
.slick-arrow::before {
  content: "";
   z-index: 2;
   border-color: #fff;
   position: relative;
   color: #fff;
  width: 1.2rem;
  height: 1.2rem;
  display: block;
}
.slick-next::before{
  border-bottom: 2px solid;
   border-left: 2px solid;
   transform: rotate(-135deg);
   right: -.3rem;
}
.slick-prev::before{
  border-bottom: 2px solid;
   border-left: 2px solid;
   transform: rotate(45deg);
   left: .85rem;
}
</style>
