<template>
  <div class="fleche-container" @click="scrollTop">
    <img src="/public/fleche-incurvee.png" alt="Fleche incurvee vers le haut" />
  </div>
</template>

<script setup>
// Fonction qui permet de faire défiler la fenêtre avec des coordonnées données ici c'est 'Top:0' et avec un défilement en douceur gârce à 'behavior'
const scrollTop = () => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};
</script>

<style scoped>
.fleche-container {
  position: fixed;
  bottom: 10px;
  right: 20px;
  cursor: pointer;
}
img {
  height: 40px;
}

img:hover {
  opacity: 0.4;
}
</style>
