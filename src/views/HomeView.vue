<template>
  <main class="home">
    <section class="landing">
      <h1>Benvinguts al meu projecte Vue.js</h1>
      <p>
        Sóc <strong>Joan Lluís Roca Sayas</strong>, estudiant d'ASIX al cicle formatiu de grau superior.
      </p>
      <p>
        Aquest projecte forma part de l'assignatura M9 – Implantació d’aplicacions web. Té com a objectiu aplicar els coneixements adquirits per desenvolupar una aplicació web moderna.
      </p>
      <p>
        L’aplicació inclou una pàgina de presentació, una connexió amb una API externa i un CRUD complet.
      </p>
    </section>
  </main>
</template>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2rem;
  background-color: #f0f8ff;
  min-height: 100vh;
}

.landing {
  background-color: white;
  color: black;
  padding: 2rem;
  border-radius: 1rem;
  max-width: 700px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

h1 {
  color: #007acc;
  margin-bottom: 1rem;
}

p {
  font-size: 1.1rem;
  margin: 0.5rem 0;
}
</style>
