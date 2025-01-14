<script setup>
import { useRouter } from "vue-router";
import EventService from "@/services/EventService.js";
import { ref } from 'vue';


const form = ref({
  name: '',
  email: '',
  password: ''
});



defineProps(["event"]);
const router = useRouter();

const register = () => {

  // verifier les input par rapports aux données de la db
  // si ok on post le nouveau participant et on redirige vers eventDetails
  // si participant existant on indique l'erreur, 
  // si les champs sont incorrect on indique l'erreur
  // si problem reseau on indique l'erreur

  router.push({
    name: "EventDetails",
  });
};
</script>
<template>
  <p>Register for the event here</p>
  <form
    id="register-form"
    @submit.prevent="register"
    method="post"
  >
    <p>
      <label for="name">Name</label>
      <input
        id="registerFormName"
        v-model="name"
        type="text"
        name="name"
      >
    </p>
    <p>
      <label for="email">Email</label>
      <input
        id="registerFormEmail"
        v-model="email"
        type="email"
        name="email"
      >
    </p>
    <button 
      type="submit"
      value="Register"
      >Register Me
    </button>
  </form>
</template>
