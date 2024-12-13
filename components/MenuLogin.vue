<template>
  <div>
    <ul class="nav justify-content-center">
      <li class="nav-item">
        <NuxtLink :to="{ name: 'index' }" class="nav-link" active-class="active"
          >Home</NuxtLink
        >
      </li>
      <li class="nav-item">
        <NuxtLink :to="{ name: 'blog' }" class="nav-link">Blog</NuxtLink>
      </li>
      <li class="nav-item">
        <NuxtLink :to="{ name: 'contacto' }" class="nav-link"
          >Contacto</NuxtLink
        >
      </li>
      <li class="nav-item">
        <NuxtLink :to="{ name: 'account-login' }" class="nav-link"
          >Login</NuxtLink
        >
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
</script>

<style scoped>
.active {
  border-bottom: 2px solid purple;
}
</style>
