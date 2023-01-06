<template>
  <div>
    <form @submit.prevent="search">
      <div class="flex gap-1 mt-20">
        <input type="text" v-model="query">
        <button>Search</button>
      </div>
    </form>
    <ul class="flex flex-wrap gap-3 mt-5">
      <li v-for="movie in movies" :key="movie.imdbID">
        <NuxtLink :to="{ name: 'movies-id', params: { id: movie.imdbID } }">
          <img :src="movie.Poster" class="rounded-md" :alt="movie.title">
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script setup>
  const query  = ref('lord of rings')
  const movies = ref([])

  async function search() {
    const { Search } = await $fetch(
      `https://www.omdbapi.com/?apikey=bb25ea2e&s=${query.value}`
    )
    movies.value = Search
  }
  search()
</script>

<style scoped>
  input {
    @apply border rounded-md border-gray-500
  }

  button {
    @apply bg-blue-500 px-4 rounded-md text-white
  }
</style>
