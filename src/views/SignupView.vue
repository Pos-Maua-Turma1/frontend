<template>
  <main class="signup-container">
    <h1>Criar conta</h1>
    <form @submit.prevent="signup" class="signup-form">
      <div id="username-container">
        <input type="text" name="Name" placeholder="Nome" />
        <input type="text" name="Last Name" placeholder="Sobrenome" />
      </div>
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
        <button>Criar conta</button>
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
const errorsignup = ref(false);

async function signup() {
  try {
    const data = "loggedIn";

    if (data === "loggedIn") {
      router.push("/home");
    } else {
      errorsignup.value = true;
    }

    console.log(data);
  } catch (error) {
    errorsignup.value = true;

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

.signup-container {
  margin-top: 20px;
  margin-bottom: 20px;
  height: 280px;
  text-align: center;
  border: 1px solid #ccc;
  box-shadow: 1px 2px #888888;
}

.signup-form {
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
