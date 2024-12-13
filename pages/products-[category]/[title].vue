<template>
  <div>
    <h1>Ruta con Parametros</h1>
    <h2>Parametro 1: {{ route.params.title }}</h2>
    <h2>Parametro 2: {{ route.params.category }}</h2>
  </div>
</template>

<script lang="ts" setup>
const route = useRoute();
definePageMeta({
  validate: (route) => {
    const regex = "r";
    const expresion = new RegExp(regex);
    return expresion.test(route.params.title);
  },
});
</script>

<style scoped>
</style>
