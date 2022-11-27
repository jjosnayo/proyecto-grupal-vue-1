<template>
  <div>
    <label>Usuario</label>
    <input type="text" v-bind:value="nombre_usuario" v-on:input="verificar_nombre"><br>
    <br>
    <label>Contraseña</label>
    <input type="text" v-bind:value="contrasenha" v-on:input="verificar_contrasenha"><br>
    <br>
    <button v-on:click="casa">Login</button>
  </div>
  <nav>
    <router-link to="/registrar">Registrarse</router-link>
  </nav>
</template>

<script>
export default {
  name: "LoginView",
  data(){
    return{
      nombre_usuario: "",
      contrasenha: ""
    }
  },
  methods: {
    casa(){
      this.$store.dispatch("accion_act_usuario", this.nombre_usuario)
      this.$store.dispatch("accion_act_contra", this.contrasenha)
      this.$router.push('/home')
    },
    verificar_nombre(e){
      this.nombre_usuario = e.target.value
    },
    verificar_contrasenha(e){
      this.contrasenha = e.target.value
    }
    // se supone que se debe verificar si los datos estan en la base de datos mediante flask usando un fetch
  }
}
</script>

<style scoped>

</style>