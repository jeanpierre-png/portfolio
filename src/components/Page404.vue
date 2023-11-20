<template>
  <div class="error-container">
    
    <img src="" alt="Error Image">
    <h1>404</h1>
    <p>La page que vous recherchez est introuvable.</p>
    <router-link :to="'/'">Retour à la page d'accueil</router-link>
    
  </div>
</template>

<style scoped>

.error-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  text-align: center;
}

img {
  max-width: 100%;
  height: auto;
  margin-bottom: 20px;
}

h1 {
  font-size: 4em;
  color: rgb(255, 0, 0);
}

p {
  font-size: 1.5em;
  color: rgb(82, 82, 82);
  margin-bottom: 20px;
}
</style>

