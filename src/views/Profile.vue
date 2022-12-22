<template>
<h1>Editar perfil</h1>   

<main class="profile-container">     
    <form @submit.prevent="profile" class="profile-form">
      <div id="profile-container">
		<div class="title">
		  <h2>Detalhes da conta</h2>
		</div>
        <input
          v-model="user"
          type="text"
          name="user"
          placeholder="Nome de usuário"
        />
		<input
          v-model="email"
          type="text"
          name="email"
          placeholder="Endereço de email"
        />
		<input
          v-model="name"
          type="text"
          name="name"
          placeholder="Nome"
        />
		<input
          v-model="lastname"
          type="text"
          name="lastname"
          placeholder="Sobrenome"
        />
		<input
          v-model="org"
          type="text"
          name="org"
          placeholder="Organização"
        />
		<input
          v-model="address"
          type="text"
          name="address"
          placeholder="Endereço"
        />		
		<input
          v-model="phone"
          type="text"
          name="phone"
          placeholder="Telefone"
        />
		<input
          v-model="birthday"
          type="text"
          name="birthday"
          placeholder="Aniversário"
        />
      </div>
      <div>        
        <button>Salvar</button>
      </div>      
    </form>
  </main>
</template>

<script setup>

</script>

<style>

h1 {
    left: 92px;
    top: 115px;
    margin-bottom: 1rem;
    font-weight: 800;
    font-size: 40px;
    color: black;
}

.profile-container {
    box-sizing: border-box;
    position: absolute;
    width: 880px;
    left: 261px;
    top: 226px;

    background: #FFFFFF;
    border: 1px solid #AAAAAA;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    text-align: center;
}

.title{
    height: 61px;
    width: 100%;
    margin-bottom: 35px;

    background: #3BC849;
    border: 1px solid #AAAAAA;
}

h2{
	font-weight: 800;
	font-size: 26px;
	text-align:left;
	padding-left: 20px;
	color: #FFFFFF;
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