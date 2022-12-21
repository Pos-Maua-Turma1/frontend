<template>
  <main>
    <div class="column-container">
      <div class="menu">
        <button>Nova nota</button>
        <button>Editar nota</button>
        <button>Arquivo</button>
        <button>Lixeira</button>
      </div>
      <ul class="list">
        <li>Nota 1</li>
        <li>Nota 2</li>
        <li>Nota 3</li>
        <li>Nota 4</li>
        <li>Nota 5</li>
      </ul>
    </div>
  </main>
</template>

<script setup></script>

<style>
.menu {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  max-height: 300px;
  margin-right: 100px;
}

.list {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  max-height: 300px;
}

.column-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  max-height: 500px;
  margin-bottom: 20px;
}
</style>
