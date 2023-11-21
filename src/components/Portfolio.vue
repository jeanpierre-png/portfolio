<template>
  <main>
    <section id="data-filters">
      <button @click="filters('*')">Toutes mes créations</button>
      <button @click="filters('cv')">Curriculum vitæ</button>
      <button @click="filters('cahier')">Cahier des charges</button>
      <button @click="filters('commentaires')">Commentaires Dynamiques</button>
    </section>

    <div id="p_creactions">
      <!--nous utilisons v-if et v-else-if pour afficher les images en fonction du type, 
      tel que défini dans le tableau isActive.-->

      <div v-for="creaction in filteredPortfolio" :key="creaction.img">
        <a href="/public/Mon Curriculum vitæ.pdf" target="_blank" v-if="creaction.tag === 'cv'">
          <img
            id="p_1"
            src="/public/Mon Curriculum vitæ.pdf"
            alt="cv"
            class="active"
          />
        </a>

        <a
          href="/public/cdc-la-socketterie.pdf"
          target="_blank"
          v-else-if="creaction.tag === 'cahier'"
        >
          <img
            id="p_2"
            src="/public/cdc-la-socketterie.pdf"
            alt="cahier-des-charges"
            class="active"
          />
        </a>

        <a
          href="/public/Commentaires.pdf"
          target="_blank"
          v-else-if="creaction.tag === 'commentaires'"
        >
          <img
            id="p_3"
            src="/public/Commentaires.pdf"
            alt="commentaires-dynamiques"
            class="active"
          />
        </a>
      </div>
    </div>
  </main>
</template>

<script setup>

import { ref, computed } from "vue";

const filter = ref("*");
const isActive = [{ tag: "cv" }, { tag: "cahier" }, { tag: "commentaires" }];

const filteredPortfolio = computed(() => {
  if (filter.value === "*") {
    return isActive;
  } else {
    return isActive.filter((image) => image.tag === filter.value);
  }
});

const filters = (tag) => {
  filter.value = tag;
};
</script>

<style scoped>
#data-filters {
  display: flex;
  justify-content: center;
  margin-top: 50px;
  margin-bottom: 50px;
  gap: 10px;
}

#data-filters button:hover {
  border: 2px solid #bda67e;
  border-radius: 20px;
  padding: 5px;
  background: #fff;
  cursor: pointer;
}

#p_creactions {
  display: flex;
  justify-content: center;
  gap: 30px;
}

img {
  height: 200px;
}

#p_1 {
  background-color: rgb(244, 99, 2);
  transition: box-shadow 0.4s; /* Ajoute une transition en douceur pour l'ombre */
}

#p_1:hover {
  box-shadow: 10px 10px 9px rgb(189, 166, 126); /* Ombre en bas et à droite */
}

#p_2 {
  background-color: rgba(52, 152, 219, 0);
  transition: box-shadow 0.4s;
}

#p_2:hover {
  box-shadow: 10px 10px 9px rgb(189, 166, 126);
}

#p_3 {
  background-color: rgba(52, 152, 219, 0);
  transition: box-shadow 0.4s;
}

#p_3:hover {
  box-shadow: 10px 10px 9px #bda67e;
}
</style>
