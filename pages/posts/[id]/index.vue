<template>
  <div class="container w-1/2 py-8 mx-auto">
    <Title>{{ post.title }} | {{ title }}</Title>
    <h3 class="text-3xl font-bold">
      <NuxtLink :to="`/posts/1`">{{ post.title }}</NuxtLink>
    </h3>
    <div class="flex items-center space-x-2 text-gray-700 post-meta">
      <div>{{ format(new Date(post.created_at), 'MMMM dd, yyyy') }}</div>
      <div>&middot;</div>
      <div>{{ post.user.name }}</div>
    </div>
    <div class="mt-4 post-content">{{ post.body }}</div>
  </div>
</template>

<script setup>
import { format } from 'date-fns'

const title = useState('title')
const route = useRoute()

const post = await useNuxtApp().$apiFetch(`/api/posts/${route.params.id}`)
</script>
