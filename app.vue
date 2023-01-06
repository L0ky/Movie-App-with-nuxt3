<template>
  <div>
    <NuxtLayout>
      <NuxtPage class="w-5/6 mx-auto"/>
    </NuxtLayout>
  </div>
</template>

<script setup>
  useHead({
    titleTemplate: (titleChunk)=>{
      return titleChunk ? `${titleChunk} - My Movie site` : 'My movie site'
    }
  })
</script>

