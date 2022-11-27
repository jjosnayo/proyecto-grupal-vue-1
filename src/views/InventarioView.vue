<template>
  <div>
    <table>
      <tr>
        <th>Usuario</th>
        <th>Producto</th>
      </tr>
      <tr v-for="compra of compras" v-bind:key="compra">
        <td>{{compra.nombre_usuario}}</td>
        <td>{{compra.nombre_producto}}</td>
      </tr>
    </table>
  </div>
  <nav>
    <router-link to="/home">Casa</router-link>
  </nav>
</template>

<script>
export default {
  name: "InventarioView",
  data(){
    return{
      compras: [
        {nombre_usuario: "usuario1", nombre_producto: "oreo"},
        {nombre_usuario: "usuario2", nombre_producto: "coca cola"},
        {nombre_usuario: "usuario3", nombre_producto: "sublime"}
      ]
    }
  }
}
</script>

<style scoped>

</style>