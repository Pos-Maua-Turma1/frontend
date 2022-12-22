<template>
<main class="password-container">
    <h1>Esqueci minha senha</h1>
    <h2>Insira um endereço de email para recuperação da senha</h2>
    <form @submit.prevent="password" class="password-form">
      <div id="email-container">
        <input
          v-model="email"
          type="text"
          name="email"
          placeholder="Endereço de email"
        />
      </div>
      <div>        
        <button>Recuperar Senha</button>
      </div>      
    </form>
  </main>
</template>

<script setup>

</script>

<style>
h1 {
    text-align: center;
    margin-bottom: 1rem;
    font-weight: 700;
    color: black;
}

h2{
    text-align: center;
    margin-bottom: 1rem;
    font-weight: 400;
    color: #AAAAAA;
}

.password-container {
    box-sizing: border-box;
    position: absolute;
    width: 918px;
    left: 261px;
    top: 226px;

    background: #FFFFFF;
    border: 1px solid #AAAAAA;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    text-align: center;
}

.password-form {
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
</style>
