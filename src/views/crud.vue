<template>
  <div class="crud">
    <h1>Gestió de Videoconsoles</h1>

    <!-- Formulari per afegir o editar -->
    <form @submit.prevent="guardarConsola">
      <input v-model="form.nom" placeholder="Nom de la consola" required />
      <input v-model="form.fabricant" placeholder="Fabricant" required />
      <input v-model="form.dataLlançament" type="date" required />
      <input v-model.number="form.ventes" placeholder="Vendes (milions)" type="number" min="0" step="0.1" required />
      <button type="submit">{{ editant !== null ? 'Actualitzar' : 'Afegir' }}</button>
    </form>

    <!-- Taula amb les consoles -->
    <table>
      <thead>
        <tr>
          <th>Nom</th>
          <th>Fabricant</th>
          <th>Data de llançament</th>
          <th>Vendes (milions)</th>
          <th>Accions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(consola, index) in consoles" :key="index">
          <td>{{ consola.nom }}</td>
          <td>{{ consola.fabricant }}</td>
          <td>{{ consola.dataLlançament }}</td>
          <td>{{ consola.ventes }}</td>
          <td>
            <button @click="editarConsola(index)">✏️ Editar</button>
            <button @click="eliminarConsola(index)">🗑️ Eliminar</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue'

const consoles = ref([])

const form = ref({
  nom: '',
  fabricant: '',
  dataLlançament: '',
  ventes: null
})

const editant = ref(null)

// 🔁 Carregar dades de localStorage en iniciar
onMounted(() => {
  const dadesGuardades = localStorage.getItem('consoles')
  if (dadesGuardades) {
    consoles.value = JSON.parse(dadesGuardades)
  }
})

// 💾 Guardar dades cada vegada que canvien
watch(consoles, (val) => {
  localStorage.setItem('consoles', JSON.stringify(val))
}, { deep: true })

function guardarConsola() {
  if (editant.value !== null) {
    consoles.value[editant.value] = { ...form.value }
    editant.value = null
  } else {
    consoles.value.push({ ...form.value })
  }

  form.value = {
    nom: '',
    fabricant: '',
    dataLlançament: '',
    ventes: null
  }
}

function editarConsola(index) {
  form.value = { ...consoles.value[index] }
  editant.value = index
}

function eliminarConsola(index) {
  consoles.value.splice(index, 1)
  if (editant.value === index) {
    form.value = {
      nom: '',
      fabricant: '',
      dataLlançament: '',
      ventes: null
    }
    editant.value = null
  }
}
</script>


<style scoped>
.crud {
  padding: 1rem;
  color: cornflowerblue;
  max-width: 900px;
  margin: auto;

  /* Fons amb imatge */
  background-image: url('../../public/Consoles.jpeg'); 
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  /* Estil extra per millorar llegibilitat */
  backdrop-filter: blur(2px);
  background-color: rgba(255, 255, 255, 0.85);
  border-radius: 10px;
}
form {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}
input {
  padding: 0.5rem;
  flex: 1;
  min-width: 180px;
}
button {
  padding: 0.5rem;
  margin: 0.2rem;
  background-color: #1abc9c;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
button:hover {
  background-color: #16a085;
}
table {
  width: 100%;
  border-collapse: collapse;
  background-color: white;
}
th, td {
  border: 1px solid #ccc;
  padding: 0.5rem;
  text-align: left;
}
th {
  background-color: #f5f5f5;
}
</style>
