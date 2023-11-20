<template>
  <div>
    <HeaderAll />
  </div>
  <main>
    
  </main>

  <RouterView />
</template>

<script setup>
import { RouterView } from "vue-router";
import HeaderAll from "./components/HeaderAll.vue";
</script>
