<template>
  <main class="login-container">
    <h1><b>Entrar</b></h1>
    <form @submit.prevent="login" class="login-form">
      <div id="user-container">
        <input v-model="email" type="text" name="email" placeholder="Endereço de email"/>
      </div>
      <div id="password-container">
        <input
          id="password"
          v-model="password"
          name="password"
          type="password"
          placeholder="Senha"
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

<style>
.login-form {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    margin: 20px 0;
}

.login-form div {
    width: 50%;
    display: flex;
    flex-direction: column;
    margin: 5px 0;
    padding: 10px;
    position: relative;

    animation: backInLeft;
    animation-duration: 1s;
}

.login-container {
  text-align: center;
  border-radius: 0px;
  margin: 200px 200px;
  padding: 20px 0px;
  border: 1px solid rgba(0, 0, 0, 0.345);
  box-shadow: 5px 10px #888888;
}

.login-form {
  margin-bottom: 1rem;
}

button {
  padding: 0.5rem 1.5rem;
  border-radius: 4px;
  border: 1px solid #ccc;
  color: rgba(255, 255, 255, 0.87);
  background-color: #3BC849;
  transition: background-color 300ms ease-in-out, transform 100ms ease-in-out;
}

button:hover {
  background-color: #33a06f;
}

button:active {
  background-color: #33a06f;
  transform: translateY(0.5px);
}
</style>
