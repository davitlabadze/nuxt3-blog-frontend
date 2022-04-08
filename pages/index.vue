<template>
    <div class="container w-1/2 py-8 mx-auto space-y-8 divide-y divide-gray-300">
    <PostItem v-for="post in posts" :key="post.id" :post="post" />
    </div>
</template>

<script setup>
const posts = await useNuxtApp().$apiFetch('posts')
</script>