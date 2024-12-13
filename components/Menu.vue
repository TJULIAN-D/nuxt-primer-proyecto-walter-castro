<template>
  <div>
    <div class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <NuxtLink
                :to="{ name: 'index' }"
                class="nav-link"
                active-class="active"
                >Home</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                :to="{ name: 'blog' }"
                class="nav-link"
                active-class="active"
                >Blog</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                :to="{ name: 'contacto' }"
                class="nav-link"
                active-class="active"
                >Contacto</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                :to="{ name: 'products' }"
                class="nav-link"
                active-class="active"
                >Products</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                :to="{ name: 'account-login' }"
                class="nav-link"
                active-class="active"
                >Login</NuxtLink
              >
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
</script>

<style scoped>
.active {
  border-bottom: 2px solid purple;
  background-color: transparent !important;
  color: #000 !important;
}
</style>
