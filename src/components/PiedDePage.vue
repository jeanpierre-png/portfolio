<template>
  <figure>
    <a href="https://github.com/jeanpierre-png" target="_blank"
      ><img src="/public/github.png" alt="logo de github"
    /></a>
  </figure>
  <date />
</template>

<script setup>
import Date from "./Date.vue";
</script>

<style scoped>
figure {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

img {
  height: 2em;
  margin: 0.4em;
}

img:hover {
  opacity: 0.4;
}
</style>
