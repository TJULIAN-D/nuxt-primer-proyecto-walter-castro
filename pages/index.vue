<template>
  <div>
    <h1>Lista de Productos</h1>
    <!-- Verificar que products esté definido antes de usarlo -->
    <div
      v-if="!Array.isArray(products) || products.length === 0"
      class="loading"
    >
      Cargando productos...
    </div>
    <div v-else class="grid">
      <div v-for="product in products" :key="product.id" class="card">
        <h2>{{ product.title }}</h2>
        <p>{{ product.description }}</p>
        <p>
          <strong>Precio: ${{ product.price }}</strong>
        </p>
        <img :src="product.thumbnail" alt="Imagen del producto" />
      </div>
    </div>
  </div>
</template>

<script setup>
console.log("qqqqqqqqqqqqqqqqqqqqqqqqqqqqqqq");

// Usar asyncData para cargar los datos en el servidor (SSR)
const { data: products } = await useAsyncData("products", async () => {
  try {
    // Realizamos la solicitud al API para obtener los productos
    const res = await fetch("https://dummyjson.com/products");
    const data = await res.json();
    console.log("-------------------dataaaaaaaa----------");

    // Devolvemos los productos para que estén disponibles en el template
    return data.products || [];
  } catch (error) {
    console.error("Error al cargar los productos:", error);
    return []; // Si ocurre un error, devolvemos un array vacío
  }
});
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(18rem, 1fr));
  gap: 1rem;
  margin-top: 1rem;
}

.card {
  border: 1px solid #ddd;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
  background: #fff;
}

.card img {
  max-width: 100%;
  height: auto;
  border-radius: 4px;
  margin-top: 1rem;
}

.loading {
  font-size: 1.2rem;
  text-align: center;
  margin-top: 2rem;
}
</style>
