<template>
  <footer>
    <div class="footer-content">
      <p>&copy; 2025 Joan Lluís Roca Sayas. Tots els drets reservats.</p>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
footer {
  background-color: #2c3e50;     /* Mateix color que el navbar */
  color: white;
  padding: 1rem 2rem;            /* Coincideix amb el padding horitzontal del navbar */
  border-top: 2px solid #34495e; /* Igual que el border-bottom del navbar */
  display: flex;
  justify-content: flex-start;   /* Text alineat a l’esquerra com els enllaços del navbar */
  align-items: center;
}

.footer-content p {
  margin: 0;
  font-size: 14px;
}
</style>
