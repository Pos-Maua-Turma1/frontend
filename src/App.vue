<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <div class="container-top-bar"> 
    <router-link to="/">
      <img
        id="logo"
        src="https://maua.br/images/logo-IMT.png"
        alt="Instituto Mauá de Tecnologia"
        style="width: 150px !important"
      />
    </router-link>

    <input type="search" placeholder="Search" class="search-field" />
    <button type="image">Menu</button>
  </div>


  <RouterView />
  <hr />
  <footer>
    <p>Note Management Ltda.</p>
    <a href="">Termos e Condições</a>
  </footer>
</template>

<style>

.search-field {
  padding: 10px 35px 10px 15px;
  border-radius: 100px;
  outline: none;
}

.container-top-bar {
  border: 1px solid #aaaaaa;
  display: flex;
  justify-content: space-between;
  margin-bottom: 18px;
  padding: 10px;
  align-items: center;
}

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
