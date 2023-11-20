<template>
  <body>
    <main>
      <div>
        <p>
          Je me nomme NOZA Jean-Pierre, je suis actuellement une formation de
          développeur web & web mobile avec le Centre européen de formation,
          plus bas, vous découvrez mes créations justement réalisées avec ma
          formation et encore plus bas un formulaire pour me joindre.
        </p>
      </div>

      <div>
        <Modal />
      </div>

      <div class="contact">
        <Contacter />
      </div>
    </main>
  </body>

  <footer>
    <PiedDePage />
  </footer>
</template>

<script setup>
import Modal from "../components/Modal.vue";
import Contacter from "../components/Contacter.vue";
import PiedDePage from "../components/PiedDePage.vue";
</script>

<style scoped>
p {
  text-align: center;
  margin-top: 100px;
  margin-bottom: 50px;
}
</style>
