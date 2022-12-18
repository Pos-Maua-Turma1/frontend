<template>
  <main>
    <form @submit.prevent="login">
      <div>
        <label>Usuário:</label>
        <input v-model="email" type="text" name="email" />
      </div>
      <div id="passwordContainer">
        <label>Senha:</label>
        <input
          id="password"
          v-model="password"
          name="password"
          type="password"
        />
      </div>
      <button>Entrar</button>
    </form>
  </main>
</template>

<script setup>
import { useRouter } from "vue-router";

import { ref } from "vue";

const router = useRouter();

const email = ref("usuario@email.com");
const password = ref("senha");
const errorLogin = ref(false);

async function login() {
  try {
    const data = "loggedIn";

    if (data === "loggedIn") {
      router.push("/home");
    } else {
      errorLogin.value = true;
    }

    console.log(data);
  } catch (error) {
    errorLogin.value = true;

    console.log(error);
  }
}
</script>

<style></style>
