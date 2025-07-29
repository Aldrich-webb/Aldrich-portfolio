<template>
  <div>
    <Navbar />
    <Landing />
    <About />
    <Projects />
    <Skills />
    <Tools />
    <Contact />
    <FooterComponent />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Landing from './components/Landing.vue';
import About from './components/About.vue';
import Projects from './components/Projects.vue';
import Skills from './components/Skills.vue';
import Tools from './components/Tools.vue';
import Contact from './components/Contact.vue';
import FooterComponent from './components/FooterComponent.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Landing,
    About,
    Projects,
    Skills,
    Tools,
    Contact,
    FooterComponent,
  },
};
</script>

<style>
/* Global styles specific to App.vue if any, though most are in main.css */
</style>