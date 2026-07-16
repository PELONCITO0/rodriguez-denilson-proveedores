
<script setup>
import EncabezadoApp from './componentes/EncabezadoApp.vue'
import FormularioProveedor from './componentes/FormularioProveedor.vue'
</script>

<template>

  <div class="encabezado-app">
    <EncabezadoApp
      titulo="Registro de Proveedores"
      subtitulo="Formulario para agregar proveedores"
    />
  </div>

 
    <FormularioProveedor/>

  

</template>

<style scoped>

  .encabezado-app {
    font-family: Arial, Helvetica, sans-serif;
  }


</style>
