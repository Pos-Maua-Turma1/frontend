<template>
  <main class="login-container">
    <h1>Entrar</h1>
    <form @submit.prevent="login" class="login-form">
      <div id="user-container">
        <input
          v-model="email"
          type="text"
          name="email"
          placeholder="Endereço de email"
        />
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
      <div>
        <a href="http://">Esqueci minha senha</a>
        <button>Entrar</button>
      </div>
      <div class="signup">
        <router-link to="/signup">Criar conta</router-link>
      </div>
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
h1 {
  text-align: center;
  margin-bottom: 1rem;
  font-weight: 700;
  color: black;
}

.login-container {
  margin-top: 20px;
  margin-bottom: 20px;
  height: 260px;
  text-align: center;
  border: 1px solid #ccc;
  box-shadow: 1px 2px #888888;
}

.login-form {
  padding: 10px;
}

input {
  width: 40%;
  padding: 0.5rem;
  border-radius: 4px;
  border: 1px solid black;
  transition: background-color 300ms ease-in-out;
  margin-bottom: 1rem;
}

button {
  padding: 0.5rem;
  border-radius: 4px;
  border: 1px solid #ccc;
  color: rgba(255, 255, 255, 0.87);
  background-color: #3bc849;
  transition: background-color 300ms ease-in-out, transform 100ms ease-in-out;
}

a {
  font-size: small;
  color: #3bc849;
}

div.signup {
  padding: 15px;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

div.signup a {
  color: #888888;
  text-decoration: underline;
  transition: 0.5s;
}
</style>
