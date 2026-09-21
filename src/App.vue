<script setup>
  import NavBar from './components/NavBar.vue'
  import Hero from './components/Hero.vue'
  import ProjectList from './components/ProjectList.vue'
  import About from './components/About.vue'
  import Contact from './components/Contact.vue'
  import AppFooter from './components/AppFooter.vue'
  import SendEmail from './components/SendEmail.vue'
  import WhatsAppComponent from './components/WhatsAppComponent.vue'
  import CertificationsSection from './components/CertificationsSection.vue'
</script>

<template>
  <NavBar />
  <Hero />
  <ProjectList />
  <CertificationsSection />
  <About />
  <Contact />
  <SendEmail />
  <AppFooter />
  <WhatsAppComponent phone="5549989167658" />
</template>
