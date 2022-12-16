<script setup></script>

<template>
  <body>
    <div class="login">
      <form>
        <h1>Entrar</h1>
        <div class="mb-3">
          <input
            type="email"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp"
            placeholder="Endereço de email"
          />
        </div>
        <div class="mb-3">
          <label for="exampleInputPassword1" class="form-label"></label>
          <input
            type="password"
            class="form-control"
            id="exampleInputPassword1"
            placeholder="Senha"
          />
        </div>
        <a href="http://">Esqueci minha senha</a>
        <button type="submit" class="btn btn-primary">Entrar</button>
      </form>
    </div>
  </body>
</template>
