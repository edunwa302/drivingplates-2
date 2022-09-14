<template>
  <section class="pb-28">
    <!-- slider -->
    <VueSlickCarousel v-bind="settings">
      <img v-for="n in 25" :key="n" :src="`/images/slide${n}.jpg`" :alt="`slide${n}`" /> 
    </VueSlickCarousel>
  </section>
</template> 
<script>
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
        speed: 1000,
        autoplaySpeed: 1000,
        cssEase: "ease-in",
        centerMode: true,
        dots: false,
        slidesToScroll: 1,
        infinite: true,
        slidesToShow: 5,
        arrows: true,
        variableWidth: true
      },
    };
  },
};
</script>
<style>
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
.slick-track
{
    display: flex !important;
}

.slick-slide
{
    height: inherit !important;
}
.slick-slide img {
  height: 25vw;
  max-height: 450px;
}
</style>
