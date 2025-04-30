<script setup>
import { RouterLink, RouterView } from 'vue-router';
import LandingPage from './components/landingpage.vue';
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue';
</script>

<template>
  <div id="app">
    <!-- Navbar sempre present -->
    <Navbar />

    <!-- Contingut principal -->
    <main>
      <div class="scale-container">
        <LandingPage />
      </div>
    </main>

    <!-- Footer sempre present -->
    <Footer />
  </div>
</template>

<style>
/* Estils globals per ocupar tota la finestra */
html, body, #app {
  margin: 0; /* Eliminem marges */
  padding: 0; /* Eliminem padding */
  height: 100%; /* Assegurem que ocupi tota la pantalla */
  display: flex; /* Fem servir Flexbox per distribuir l'espai */
  flex-direction: column; /* Organitzem els elements de manera vertical */
  background-color: #e0e0e0;
  overflow-x: hidden; /* Assegurem que no hi hagi desplaçament horitzontal */
}

#app {
  min-height: 100vh; /* Assegurem que l'app ocupi almenys tota l'altura de la finestra */
  display: flex;
  flex-direction: column; /* Els elements fills es col·loquen de dalt a baix */
  width: 100%; /* Assegurem que l'amplada sigui 100% */
}

main {
  flex-grow: 1; /* Fa que el contingut central ocupi tot l'espai disponible */
  width: 100%; /* Assegurem que el main ocupa tota l'amplada */
  display: flex;
  justify-content: center; /* Centrem el contingut */
  align-items: center; /* Centrem el contingut verticalment */
  overflow: hidden; /* Eliminem el desplaçament */
}

.scale-container {
  width: 100%; /* Assegurem que el LandingPage ocupi tota l'amplada */
  height: 100%; /* Assegurem que ocupi tota l'altura */
  transform: scale(1.5); /* Ajustem l'escala per evitar l'excés d'escala */
  transform-origin: top center; /* Centrem l'escala des de dalt */
}

header {
  line-height: 1.5;
  width: 100%; /* Assegurem que el header ocupi tota l'amplada */
}

footer {
  background-color: #2c3e50;
  color: white;
  padding: 1rem;
  text-align: center;
  margin-top: 2rem;
  width: 100%; /* Assegurem que el footer ocupi tota l'amplada */
}

footer .footer-content p {
  margin: 0;
}

/* Navbar personalitzat */
nav {
  display: flex;
  justify-content: flex-start;
  gap: 1rem;
  font-size: 16px;
  margin-top: 1rem;
  flex-wrap: wrap;
  width: 100%; /* Assegurem que el navbar ocupi tota l'amplada */
}

nav a {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
  transition: background-color 0.3s ease;
  border-radius: 5px;
}

nav a.router-link-exact-active {
  font-weight: bold;
  border-bottom: 2px solid #1abc9c;
}

nav a:hover {
  background-color: #1abc9c;
  border-radius: 5px;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    width: 100%;
  }

  nav {
    text-align: right;
    margin-top: 0;
    width: 100%; /* Assegurem que ocupi tota l'amplada */
  }
}
</style>
