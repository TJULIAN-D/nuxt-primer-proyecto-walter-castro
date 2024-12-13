

<template>
  <div>
    <div class="grid">
      <Card v-for="product in products" :key="product.id" :="product" />
    </div>
  </div>
</template>

<script setup >
//importar desde la carpeta server toda la api
// import { products } from "~/server/api/products.json";
import { onMounted, ref } from "vue";
const products = ref([]);

onMounted(async () => {
  const res = await fetch("https://dummyjson.com/products");
  let data = await res.json();
  products.value = await data.products;

  //console.log(products);
});
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(18rem, 1fr));
}
</style>
