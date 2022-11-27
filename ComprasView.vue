<template>
  <div class="compras">
    <h1>Esta es la página de compras</h1>
    <table>
      <tr>
        <th>Nombre</th>
        <th>Tipo</th>
      </tr>
      <tr v-for="producto of productos" v-bind:key="producto">
        <td  v-if="producto.nombre_usuario !== $store.state.mi_usuario">{{producto.nombre_producto}}</td>
        <td  v-if="producto.nombre_usuario !== $store.state.mi_usuario">{{producto.tipo_producto}}</td>
        <button v-on:click="comprar(producto.codigo)">Comprar</button>
        <td></td>
      </tr>
    </table>
  </div>
  <nav>
    <router-link to="/home">Casa</router-link>
  </nav>
</template>

<script>
export default {
  name: "ComprasView",
  data(){
    return{
      productos: [
        {nombre_producto: "glasita", tipo_producto: "galleta"},
        {nombre_producto: "inca cola", tipo_producto: "gaseosa"},
        {nombre_producto: "princesa", tipo_producto: "chocolate"}
      ],
      comprado: ""
    }
  },
  methods: {
    comprar(p){
      this.comprado = p
      // se supone que la función debe crear una compra con los datos del producto seleccionado,
      // asignarlos a comprado y guardarlo en la base de datos mediante flask usando un fetch
    }
  }
  // se supone que productos debe contener todos los productos registrados de la base de datos mediante flask
  // usando un fetch y created, se debe filtrar en el template los productos que no sean del usuario con el que
  // te acabas de logear
}
</script>

<style scoped>

</style>