<template>
  <div>
    <small>
      Dernière mise à jour le :
      <p>{{ Dateview }}</p>
    </small>
  </div>
</template>

<script setup>
const date = new Date();

let Dateview = date.toLocaleDateString("fr");
</script>

<style scoped>
small {
  display: flex;
  justify-content: center;
}

p {
  margin: 0;
  padding-left: 2px;
}
</style>
