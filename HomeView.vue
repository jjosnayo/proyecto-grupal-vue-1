<template>
  <div class="home">
    <h1>"Bienvenido a Utec Shop"</h1>
    <div v-for="usuario of usuarios" v-bind:key="usuario">
      <h2 v-if="usuario.nombre_usuario === $store.state.mi_usuario">Usuario: {{usuario.nombre_usuario}}</h2>
      <h2 v-if="usuario.contrasenha === $store.state.mi_contrasenha">Contraseña: {{usuario.contrasenha}}</h2>
    </div>
  </div>
  <nav>
    <router-link to="/compras">Comprar</router-link> |
    <router-link to="/ventas">Vender</router-link> <br>
    <router-link to="/">Logout</router-link>
  </nav>
</template>

<script>
export default {
  name: 'HomeView',
  data(){
    return{
      usuarios: [
        {nombre_usuario: "usuario1", contrasenha: "a101010a"},
        {nombre_usuario: "usuario2", contrasenha: "b202020b"},
        {nombre_usuario: "usuario3", contrasenha: "c303030c"}
      ]
    }
  }
  // se supone que usuarios debe contener todos los usuarios registrados recibiendolos de la base de datos
  // mediante flask usando un fetch y created
  // se debe filtrar en el template el usuario con el que te acabas de logear o registrar
}
</script>
