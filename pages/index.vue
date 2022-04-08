<template>
    <div class="container w-1/2 py-8 mx-auto space-y-8 divide-y divide-gray-300">
    <PostItem v-for="n in 10" :key="n"/>
    </div>
</template>