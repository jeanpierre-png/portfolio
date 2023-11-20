<template>
  <div>
    <div v-for="image in images" :key="image.title" class="bloc-modal">

      <!-- Overlay pour fermer la modal en dehors d'elle -->
      <div v-if="isModalOpen && selecteImage && selecteImage.title === image.title" class="overlay" @click="closeModal"></div>

      <!-- Modal -->
      <div v-if="isModalOpen && selecteImage && selecteImage.title === image.title" class="modal">
        <button class="close-btn" @click="closeModal">X</button>
        <h2>{{ modalTitle }}</h2>
       <div class="image-modal">
          <img :src="modalLink" :alt="modalTitle">
        </div>
        <p>{{ modalDate }}</p>
        <p>{{ modalTechnologies }}</p>
        <a :href="modalLink" target="_blank">Visualiser le fichier PDF</a>
        <a v-if="modalRepoLink" :href="modalRepoLink" target="_blank">Repository GitHub</a>
      </div>
    </div>

    <div class="portfolio">
      <img @click="openModal(images[0])" src="/public/Mon Curriculum vitæ.pdf" alt="Mon CV"> 
      <img @click="openModal(images[1])" src="/public/cdc-la-socketterie.pdf" alt="Cahier des charges">
      <img @click="openModal(images[2])" src="/public/Commentaires.pdf" alt="Commentaires">
    </div>
  </div>
</template>

<script setup>

import { ref } from "vue";

const isModalOpen = ref(false);
const selecteImage = ref(null);
const modalTitle = ref("");
const modalDate = ref("");
const modalTechnologies = ref("");
const modalLink = ref("");
const modalRepoLink = ref("");

const images = [
  {
    title: "Mon Curriculum vitæ",
    date: "Date de création: 17-07-2023",
    technologies: "Technologies utilisées: HTML, CSS",
    link: "/public/Mon Curriculum vitæ.pdf",
    repoLink: "https://github.com/jeanpierre-png/cv.git"
  },
  {
    title: "Cahier des charges",
    date: "Date de création: 04-09-2023",
    technologies: "Technologies utilisées: Canva, Excel, PowerPoint",
    link: "/public/cdc-la-socketterie.pdf",
  },
  {
    title: "Dynamiser un espace commentaire",
    date: "Date de création: 18-09-2023",
    technologies: "Technologies utilisées: HTLM, CSS, JavaScript",
    link: "/public/Commentaires.pdf",
    repoLink: "https://github.com/jeanpierre-png/dynamiser_un_espace_commentaire.git"
  }
];

const openModal = (image) => {
  // Mettez à jour les valeurs avec les données du projet
  selecteImage.value = image;
  modalTitle.value = image.title;
  modalDate.value = image.date;
  modalTechnologies.value = image.technologies;
  modalLink.value = image.link;
  modalRepoLink.value = image.repoLink || null;
  isModalOpen.value = true;
};

const closeModal = () => {
  isModalOpen.value = false;
  selecteImage.value = null;
};

</script>

<style scoped>

.bloc-modal {
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.overlay {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.7);
}

.modal {
  position: fixed;
  background: #f1f1f1;
  color: #333;
  top: 20%;
  padding: 50px;
}

.close-btn{
  position: absolute;
  top: 10px;
  right: 10px;
  color: rgb(0, 0, 0);
}

.close-btn:hover{
  background-color: rgb(255, 0, 0);
  color: white;
  cursor: pointer;
}

h2{
  text-align: center;
}

.image-modal{
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
}

img {
  height: 200px;
  width: 200px;
  border-radius: 100%;
  border: 1px solid #333;
  margin: 20px;
}

.portfolio{
  margin-top: 100px;
  margin-bottom: 100px;
  cursor: pointer;
  background-color: rgba(52, 152, 219, 0);
  transition: box-shadow 0.4s;
}

.portfolio :hover{
  box-shadow: 10px 10px 9px #bda67e;
}

a{
  margin-top: 16px;
  margin-bottom: 16px;
  display: flex;
}
</style>
