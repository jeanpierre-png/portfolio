<template>
  <header>
    <div>
      <Logo/>
    </div>

    <div>
      <NavBar/>
    </div>
  </header>

  <main>
    <BoutonRetourTop/>
  </main>
</template>

<script setup>
import Logo from "./Logo.vue";
import NavBar from "./NavBar.vue";
import BoutonRetourTop from "./BoutonRetourTop.vue";
</script>
