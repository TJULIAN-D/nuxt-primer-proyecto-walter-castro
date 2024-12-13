<template>
  <div class="container">
    <div class="row">
      <h1>My Account</h1>
      <div class="col-6">
        <NuxtLink
          :to="{
            name: 'account-login',
          }"
        >
          Login</NuxtLink
        >
        <NuxtLink
          :to="{
            name: 'account-register',
          }"
        >
          Register</NuxtLink
        >
      </div>
      <div class="col-6">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
definePageMeta({
  layout: "authentication",
});
</script>

<style scoped>
</style>
