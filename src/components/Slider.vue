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
