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
  <h2>Registro de Proveedores</h2>
  <input v-model="nombreEmpresa" placeholder="Nombre de la empresa" />
  <input v-model="nombreContacto" placeholder="Nombre del contacto" />
  <input v-model="telefono" placeholder="Teléfono" />
  <input v-model="correo" placeholder="Correo electrónico" />
  <select v-model="categoria">
    <option value="">Seleccione una categoría</option>
    <option value="Alimentos">Alimentos</option>
    <option value="Tecnología">Tecnología</option>
    <option value="Ropa">Ropa</option>
    <option value="Servicios">Servicios</option>
    <option value="Otros">Otros</option>
  </select>
  <input v-model="ciudad" placeholder="Ciudad" />
  <button @click="guardarProveedor">Guardar</button>

  <ul v-if="proveedor.length > 0">

    <li v-for="proveedor in proveedor">
      {{ proveedor.nombreEmpresa }} - {{ proveedor.nombreContacto }} - {{ proveedor.telefono }} -
      {{ proveedor.correo }} - {{ proveedor.categoria }} - {{ proveedor.ciudad }}
    </li>

    
  </ul>

  <p v-else>No hay proveedores registrados.</p>
</template>

<style scoped>

</style>
