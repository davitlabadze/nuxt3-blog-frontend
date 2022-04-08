<template>
    <div class="py-8 post-container">
        <h3 class="text-3xl font-bold"><NuxtLink :to="`/posts/${props.post.id}`" >
            {{ props.post.title }}</NuxtLink></h3>
        <div class="flex items-center space-x-2 text-gray-700 post-meta">
            <div>{{ format(new Date(props.post.created_at), 'MMMM dd, yyyy') }}</div>
            <div>&middot;</div>
            <div>{{ props.post.user.name }}</div>
        </div>
        <div class="mt-4 post-preview loading-relaxed line-clamp-3">
            {{ props.post.body }}
        </div>
        <div class="mt-4">
            <NuxtLink :to="`/posts/${props.post.id}`" class="inline-block px-4 py-2 text-white bg-blue-700 rounded hover:bg-blue-800">
            Read More</NuxtLink>
        </div>
    </div>
</template>

<script setup>

import { format } from 'date-fns'

const props = defineProps({
    post:Object,
})
</script>