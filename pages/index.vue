<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())

useSeoMeta({
  title: page.value.title,
  ogTitle: page.value.title,
  description: page.value.description,
  ogDescription: page.value.description
})

defineOgImage({
  component: 'Landing',
  //@ts-ignore
  title: page.value.title,
  description: page.value.description
})
</script>

<template>
  <div>
    <h1>
      Welcome! {{ page.title }}
    </h1>
    <p>{{ page.description }}</p>
  </div>
</template>
