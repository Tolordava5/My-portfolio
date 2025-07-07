<script setup>
import Header from "./Components/Header.vue"
import Home from "./Components/Home.vue"
import About from "./Components/About.vue"
import Skills from "./Components/Skills.vue"
import Contact from "./Components/Contact.vue"
import Projects from "./Components/Projects.vue"
</script>

<template>
  <div>
    <Header />
    
    <main class="main-content">
      <section id="home" class="section"><Home /></section>
      <section id="about" class="section"><About /></section>
      <section id="skills" class="section"><Skills /></section>
      <section id="projects" class="section"><Projects /></section>
      <section id="contact" class="section"><Contact /></section>
    </main>
  </div>
</template>

<style scoped>
.main-content {
  padding-top: 100px; 
}
</style>