<template>
  <div class="min-h-[150vh]">
    <jumbotron />
    <page-body/>
    <footer-section />
  </div>
</template>

<script>
import Jumbotron from "./components/Jumbotron.vue";
import PageBody from "./components/PageBody.vue"
import FooterSection from './components/FooterSection.vue';

export default {
  components: {
    Jumbotron,
    PageBody,
    FooterSection,
  }
}

</script>

<style scoped></style>
