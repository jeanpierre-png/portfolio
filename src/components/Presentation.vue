<template>
  <body>
    <main>
      <div class="info-general">
        <ul class="bloc-1">
          <h1>Information Genéral</h1>
          <li class="prenom">Prénom : {{ prenom }}</li>
          <li class="adresse">Addresse : {{ adresse }}</li>
          <li class="date-de-naissance">
            Date de naissance : {{ dateDeNaissance }}
          </li>
          <li class="mail">
            <a href="mailto:jpnoza1@gmail.com">E-mail : {{ email }}</a>
          </li>
          <li class="numero">
            <a href="tel:069410203">Numéro de portable : {{ portable }}</a>
          </li>
        </ul>
      </div>

      <div class="bloc-2">
        <h2>Description</h2>
        <p>
          Je suis actuellement salarié dans une boite prive en tant que chimiste
          et en parallèle, je poursuis une formation de Développeur web. Vous
          allez voir ici mes débuts de réalisation effectuer avec ma formation.
        </p>
      </div>
    </main>
  </body>
</template>

<script setup>
const props = defineProps({
  prenom: {
    type: String,
    default: "Jean-Pierre",
  },

  adresse: {
    type: String,
    default: "Cayenne",
  },

  dateDeNaissance: {
    type: String,
    default: "09/10/1996",
  },

  email: {
    type: String,
    default: "jpnoza1@gmail.com",
  },

  portable: {
    type: String,
    default: "0694010203",
  },
});
</script>

<style scoped>
main {
  display: flex;
}
.info-general {
  display: flex;
  justify-content: left;
  align-items: center;
}
.bloc-1 {
  background: #bda67e;
  display: flex;
  border-radius: 20px;
  width: 330px;
  height: 600px;
  margin-left: 17px;
  margin-right: 17px;
  justify-content: space-around;
  padding-right: 40px;
  text-align: left;
  flex-direction: column;
}
.bloc-2 {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h1,
h2 {
  display: flex;
  justify-content: center;
}

p {
  display: flex;
  padding-left: 20px;
  text-align: center;
}

a {
  text-decoration: none;
  color: black;
}
</style>
