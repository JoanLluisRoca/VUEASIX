<template>
  <div class="page">

    <main class="p-4">
      <section class="intro">
        <h1>Dades de l'API</h1>
        <p>
          Aquesta pàgina mostra una llista d'usuaris extreta de l'API pública de JSONPlaceholder.
          Les dades inclouen informació com l'ID, nom, correu electrònic, telèfon i ciutat de cada usuari.
        </p>
      </section>

      <section class="dades-api">
        <div v-if="loading">Carregant dades...</div>
        <div v-else-if="error">Hi ha hagut un error: {{ error }}</div>

        <table v-else class="api-table">
          <thead>
            <tr>
              <th>ID</th>
              <th>Nom</th>
              <th>Correu</th>
              <th>Telèfon</th>
              <th>Ciutat</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in dades" :key="item.id">
              <td>{{ item.id }}</td>
              <td>{{ item.name }}</td>
              <td>{{ item.email }}</td>
              <td>{{ item.phone }}</td>
              <td>{{ item.address.city }}</td>
            </tr>
          </tbody>
        </table>
      </section>
    </main>

  </div>
</template>

<script setup>
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
import { ref, onMounted } from 'vue'

const dades = ref([])
const loading = ref(true)
const error = ref(null)

onMounted(async () => {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    if (!res.ok) throw new Error('Error en carregar les dades')
    dades.value = await res.json()
  } catch (e) {
    error.value = e.message
  } finally {
    loading.value = false
  }
})
</script>

<style scoped>
.page {
  display: flex;
  flex-direction: column;
  min-height: 100vh;

  background-image: url('/vue.png'); /* Ruta relativa a /public */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

/* Opcional: fons translúcid per millorar llegibilitat */
main {
  flex: 1;
  color: black;
  background-color: rgba(255, 255, 255, 0.9); /* lleuger blanc translúcid */
  padding: 1rem;
  border-radius: 10px;
  margin: 1rem;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}


.intro {
  margin-bottom: 1.5rem;
}

.api-table {
  width: 100%;
  border-collapse: collapse;
  background-color: white;
  color: black;
}

.api-table th, .api-table td {
  border: 1px solid #ccc;
  padding: 0.5rem;
  text-align: left;
}

.api-table th {
  background-color: #f5f5f5;
}
</style>
