<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <img
    id="logo"
    src="https://maua.br/images/logo-IMT.png"
    alt="Instituto Mauá de Tecnologia"
    style="width: 150px !important"
  />
  <RouterView />
  <br />
  <hr />
  <div>
    <p>Note Management Ltda.</p>
  </div>
</template>

<style>
p {
  margin-top: 2px;
  font-size: smaller;
  color: gray;
}
</style>