<script setup>
import { ref } from 'vue'

const nombreEmpresa = ref('')
const nombreContacto = ref('')
const telefono = ref('')
const correo = ref('')
const categoria = ref('')
const ciudad = ref('')

const proveedor = ref([])

function guardarProveedor() {

  proveedor.value.push({
    nombreEmpresa: nombreEmpresa.value,
    nombreContacto: nombreContacto.value,
    telefono: telefono.value,
    correo: correo.value,
    categoria: categoria.value,
    ciudad: ciudad.value,
  })

  nombreEmpresa.value = ''
  nombreContacto.value = ''
  telefono.value = ''
  correo.value = ''
  categoria.value = ''
  ciudad.value = ''
}
</script>

<template>


<form @submit.prevent="guardarProveedor">
    <h2>Registro de Proveedores</h2>
    <input v-model="nombreEmpresa" placeholder="Nombre de la empresa" required="true" />
    <input v-model="nombreContacto" placeholder="Nombre del contacto" required="true" />
    <input v-model="telefono" placeholder="Teléfono" required="true" />
    <input v-model="correo" placeholder="Correo electrónico" required="true" />
    <select v-model="categoria" required="true">
    <option value="">Seleccione una categoría</option>
    <option value="Alimentos">Alimentos</option>
    <option value="Tecnología">Tecnología</option>
    <option value="Ropa">Ropa</option>
    <option value="Servicios">Servicios</option>
    <option value="Otros">Otros</option>
    </select>
    <input v-model="ciudad" placeholder="Ciudad" required="true" />
    <button type="submit">Guardar</button>
</form>


  <ul v-if="proveedor.length > 0">

    <li v-for="proveedor in proveedor">
      {{ proveedor.nombreEmpresa }} - {{ proveedor.nombreContacto }} - {{ proveedor.telefono }} -
      {{ proveedor.correo }} - {{ proveedor.categoria }} - {{ proveedor.ciudad }}
    </li>

    
  </ul>

  <p v-else>No hay proveedores registrados.</p>

</template>

<style scoped>
    form {
        max-width: 400px;
        margin: 0 auto;
        padding: 20px;
        background-color: #f9f9f9;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    input, select {
        display: block;
        margin-bottom: 10px;
        padding: 8px;
        width: 100%;
        box-sizing: border-box;
        border: 1px solid #ccc;
        border-radius: 10px;
    }
    button {
        display: block;
        margin-top: 10px;
        background-color: #4CAF50;
        border: none;
        border-radius: 10px;
        color: white;
        padding: 10px 20px;
        text-align: center;
        font-size: 16px;
        cursor: pointer;
        width: 100%;
    }

    ul {
        list-style-type: none;
        padding: 0;
        text-align: center;
    }
    li {
        margin-bottom: 5px;
    }

    p {
        text-align: center;
        font-style: italic;
    }

</style>
