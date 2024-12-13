<template>
  <div class="card" style="width: 18rem">
    <img
      :src="thumbnail"
      class="card-img-top"
      alt="..."
      style="aspect-ratio: 10 / 6; object-fit: contain"
    />
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">
        {{ description }}
      </p>
      <NuxtLink
        :to="{
          name: 'products-category-title',
          params: {
            title: slug,
            category: category,
          },
        }"
        >Ver Producto</NuxtLink
      >
    </div>
  </div>
</template>

<script  setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  title: {
    type: String,
    require: true,
  },
  thumbnail: {
    type: String,
    require: true,
  },
  description: {
    type: String,
    require: true,
  },
  category: {
    type: String,
    require: true,
  },
});

const slug = "iVe crEam".toLowerCase().split(" ").join("-");
</script>

<style scoped>
</style>
