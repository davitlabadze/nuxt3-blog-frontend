<template>

    <div class="container w-1/2 py-8 mx-auto">
        <Title>{{ $route.params.id }} | {{ title }} </Title>
        <h3 class="text-3xl font-bold"><NuxtLink :to="`/posts/1`" >
            Title of Post</NuxtLink>
        </h3>
        <div class="flex items-center space-x-2 text-gray-700 post-meta">
            <div>APR 8, 2022</div>
            <div>&middot;</div>
            <div>David Labadze</div>
        </div>
        <div class="mt-4 post-content">
            {{ $route.params.id }} consectetur adipisicing elit. Nam odit atque cum incidunt quaerat provident velit maxime ipsum, quo enim est? Et est vero, eaque illo iusto laborum officiis autem?
        </div>
    </div>

</template>

<script setup>
const title = useState('title')
</script>