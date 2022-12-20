<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <router-link to="/">
    <img
      id="logo"
      src="https://maua.br/images/logo-IMT.png"
      alt="Instituto Mauá de Tecnologia"
      style="width: 150px !important"
    />
  </router-link>

  <RouterView />
  <hr />
  <footer>
    <p>Note Management Ltda.</p>
    <a href="">Termos e Condições</a>
  </footer>
</template>

<style>
p {
  margin-top: 2px;
  font-size: smaller;
  color: gray;
}

footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 15px;
}

footer a {
  font-size: 10px;
}
</style>
