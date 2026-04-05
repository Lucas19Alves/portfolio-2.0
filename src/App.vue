<script setup lang="ts">
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';
import Header from './components/Header.vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Skills from './components/Skills.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import BackToTop from './components/BackToTop.vue';

onMounted(() => {
  AOS.init({
    duration: 1000,
    easing: 'ease-in-out',
    once: true,
  });
});
</script>

<template>
  <div class="min-h-screen">
    <Header />
    <main>
      <Hero />
      <About />
      <Skills />
      <Projects />
      <Contact />
    </main>
    <Footer />
    <BackToTop />
  </div>
</template>