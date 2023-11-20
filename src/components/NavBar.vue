<template>
  <header>
    <div class="menu_nav">
      <nav class="menu_active">
        <ul>
          <li
            v-for="menu in menuActive"
            :key="menu.tag"
            :class="{ active: menu.isActive }"
            @click="activateMenu(menu)"
          >
            <router-link :to="`/${menu.tag}`">{{ menu.tag }}</router-link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const menuActive = ref([
  { tag: "Presentation", isActive: false },
  { tag: "Portfolio", isActive: false },
  { tag: "Contacter", isActive: false },
]);

// Fonction qui active le menu sur lequelle utilisateur a cliqué

function activateMenu(selectedMenu) {
  menuActive.value.forEach((menu) => {
    menu.isActive = menu === selectedMenu;
  });
}
</script>

<style scoped>
.menu_nav {
  display: flex;
  padding-left: 36px;
  padding-right: 36px;
}
.menu_active {
  width: 100%;
  height: 100%;
  border-radius: 20px 20px 30px 30px;
  border: 1px solid white;
  background: #515e73;
}
.active {
  text-decoration: underline;
  color: #bda67e;
}

ul {
  display: flex;
  justify-content: space-around;
  padding: initial;
}

a {
  text-decoration: none;
  color: white;
}
</style>
