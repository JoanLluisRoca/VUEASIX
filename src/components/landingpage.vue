<template>
    <div>
  
      <!-- Contingut de la Landing Page -->
      <section class="landing-content">
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
  
        <div class="cta">
          <p>Fes clic al botó per saber més!</p>
          <RouterLink to="/about" class="btn">Més informació</RouterLink>
        </div>
      </section>
  
    </div>
  </template>
  
  <script setup>
  </script>
  
  <style scoped>
  /* Estils per la landing page */
  .landing-content {
    text-align: center;
    margin-top: 3rem;
  }
  
  .landing-content h1 {
    font-size: 3rem;
    color: #0057b8;
  }
  
  .landing-content p {
    font-size: 1.2rem;
    margin-top: 1rem;
    color: black;
  }
  
  .cta {
    margin-top: 2rem;
  }
  
  .cta .btn {
    display: inline-block;
    padding: 0.8rem 2rem;
    background-color: #0057b8;
    color: white;
    font-size: 1rem;
    text-decoration: none;
    border-radius: 5px;
    margin-top: 1rem;
  }
  
  .cta .btn:hover {
    background-color: #003b8b;
  }
  
  .home {
    margin-top: 2rem;
  }
  
  .landing {
    background-color: #f0f8ff;
    padding: 2rem;
    border-radius: 10px;
    max-width: 800px;
    margin: 0 auto;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  }
  
  .landing h1 {
    color: #0057b8;
    margin-bottom: 1rem;
  }
  
  .landing p {
    font-size: 1rem;
    line-height: 1.6;
  }
  </style>
  