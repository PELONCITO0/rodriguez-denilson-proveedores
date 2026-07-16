<script setup>

defineProps({
  titulo: {
    type: String,
    required: true
  },
  subtitulo: {
    type: String,
    required: true
  },
})
</script>

<template>
  <header class="encabezado-app">
    <h1>{{ titulo }}</h1>
    <h2>{{ subtitulo }}</h2>
  </header>
</template>

<style scoped>
.encabezado-app {
  text-align: center;
  margin-bottom: 20px;
  background-color:   black;
  padding: 40px;
}

.encabezado-app h1 {
  font-size: 2em;
  margin: 0;
  color: white;
}

.encabezado-app h2 {
  font-size: 1.5em;
  margin: 0;
  color: white;
}
</style>
