<template>
  <header>
    <div class="navbar-container">
      <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="50" height="50" />
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <router-link to="/api">Dades API</router-link>
        <RouterLink to="/crud">CRUD</RouterLink>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { RouterLink } from 'vue-router';
</script>

<style scoped>
header {
  background-color: #2c3e50;
  color: white;
  border-bottom: 2px solid #34495e;
  padding: 0.5rem 1rem;
}

/* Contenidor general del navbar */
.navbar-container {
  display: flex;
  align-items: center;
}

/* Logo alineat a l'esquerra */
.logo {
  margin-right: 1rem;
}

/* Enllaços horitzontals a l'esquerra */
nav {
  display: flex;
  gap: 1rem;
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
  color: #fff;
}
</style>
