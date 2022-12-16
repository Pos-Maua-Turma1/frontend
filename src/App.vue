<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>
  <RouterView />
  <footer>
    <hr />
    <p>NomeDoApp Ltda.</p>
    <a href="http://">Termos e condições</a>
  </footer>
</template>

<style scoped></style>
