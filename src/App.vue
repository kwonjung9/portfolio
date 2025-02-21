<template>
  <div class="app">
    <Mainpage @scroll-to-section="scrollToSection"/>
    <section ref="about"><AboutMe/></section>
    <section ref="website"><Website/></section>
    <section ref="design"><Design/></section>
    <section ref="contact"><Contact/></section>
  </div>
</template>

<script setup>
import { ref } from 'vue';

import AboutMe from './components/AboutMe.vue';
import Contact from './components/Contact.vue';
import Mainpage from './components/Mainpage.vue';
import Website from './components/Website.vue';
import Design from './components/Design.vue';

const about = ref(null);
const website =ref(null);
const design = ref(null);
const contact =ref(null);


const scrollToSection = (section) => {
  if (section === 'about' && about.value) {
    about.value.scrollIntoView({ behavior: 'smooth' });
  } else if (section === 'website' && website.value) {
    website.value.scrollIntoView({ behavior: 'smooth' });
  } else if (section === 'design' && design.value) {
    design.value.scrollIntoView({ behavior: 'smooth' });
  }else if (section === 'contact' && contact.value) {
    contact.value.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<style lang="scss" scoped>

</style>