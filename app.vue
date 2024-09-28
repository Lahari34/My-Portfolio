<template>
  <div>
    <Header />
    <Intro />
    <About />
    <Projects />
    <Contact />
    <Nuxt />
    <Footer />

  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Intro from './components/Intro.vue';
import About from './components/About.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue'

export default {
  components: {
    Header,
    Intro,
    About,
    Projects,
    Contact,
    Footer
  }
}
</script>

