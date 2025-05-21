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
    <section class="landing">
      <p>
        Sóc <strong>Joan Lluís Roca Sayas</strong>, estudiant del cicle formatiu de grau superior d'ASIX (Administració de Sistemes Informàtics en Xarxa).
      </p>
      <p>
        En el futur, m'agradaria especialitzar-me en el món de les xarxes i la ciberseguretat, àrees que considero essencials per al bon funcionament i protecció de les infraestructures tecnològiques.
      </p>
      <p>
        Aquest projecte forma part de l’assignatura M9 – Implantació d’aplicacions web. L’objectiu és aplicar els coneixements adquirits per desenvolupar una aplicació web moderna amb Vue.js.
      </p>
      <p>
        L’aplicació inclou una pàgina de presentació, una connexió amb una API externa i un CRUD complet desenvolupat pel propi alumne.
      </p>
    </section>

  </main>
</template>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2rem;
  min-height: 100vh;

  background-image: url('/baixa.jpeg'); /* Ruta relativa a public */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.landing {
  background-color: rgba(255, 255, 255, 0.9); /* Fons blanc translúcid per llegibilitat */
  color: black;
  padding: 2rem;
  border-radius: 1rem;
  max-width: 700px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  margin-bottom: 2rem;
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
