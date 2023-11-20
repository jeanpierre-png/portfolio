<template>
  <div>
    <h1>Contactez-moi</h1>

    <form @submit.prevent="submitForm">
      <div>
        <label for="name">Nom :</label>
        <input
          type="text"
          id="name"
          placeholder="Nom"
          v-model="name"
          required
        />
      </div>

      <div>
        <label for="prenom">Prénom :</label>
        <input
          type="text"
          id="prenom"
          placeholder="Prénom"
          v-model="prenom"
          required
        />
      </div>

      <div>
        <label for="objet">Objet :</label>
        <input
          type="objet"
          id="objet"
          placeholder="objet"
          v-model="objet"
          required
        />
      </div>

      <div>
        <label for="email">E-mail :</label>
        <input
          type="email"
          id="email"
          placeholder="E-mail"
          v-model="email"
          required
        />
      </div>

      <div>
        <label for="message">Message :</label>
        <span id="message-max"> Max. 500 caractères</span>
        <textarea
          id="message"
          name="message"
          cols="30"
          rows="10"
          maxlength="500"
          v-model="message"
          aria-describedby="message-max"
          required
        ></textarea>
      </div>

      <div>
        <button type="submit">Envoyer</button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const name = ref("");
const prenom = ref("");
const objet = ref("");
const email = ref("");
const message = ref("");

const submitForm = () => {
  // Réinitialiser le formulaire après soumission
  name.value = "";
  prenom.value = "";
  objet.value = "";
  email.value = "";
  message.value = "";
};
</script>

<style scoped>
h1 {
  text-align: center;
}

form {
  width: 300px;
  margin: 20vh auto 0 auto;
  margin-top: 20px;
  padding: 20px;
  background-color: #bda67e;
  border-radius: 4px;
  font-size: 12px;
}

div {
  margin-bottom: 15px;
}

label {
  margin-bottom: 5px;
}

input,
textarea {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 4px;
}

textarea {
  resize: vertical;
}

button {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
  color: white;
  background-color: #515e73;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
</style>
