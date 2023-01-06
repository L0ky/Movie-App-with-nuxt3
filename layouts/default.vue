<template>
    <nav class="flex gap-5 text-lg">
      <NuxtLink active-class="font-semibold" to="/">Home</NuxtLink>
      <NuxtLink active-class="font-semibold" to="/movies">Movies</NuxtLink>
      <NuxtLink active-class="font-semibold" to="https://vueschool.io">Vue School</NuxtLink>
      <NuxtLink v-if="!user.isLoggedIn" to="/login">Login</NuxtLink>
      <a href="#" v-else @click.prevent="user.isLoggedIn = false">Logout</a>
    </nav>
    <slot></slot>
</template>

<script setup>
const user = useUser()
</script>