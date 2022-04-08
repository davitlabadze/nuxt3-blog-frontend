<template>
    <div class="py-8 post-container">
        <h3 class="text-3xl font-bold"><NuxtLink :to="`/posts/1`" >
            Title of Post</NuxtLink></h3>
        <div class="flex items-center space-x-2 text-gray-700 post-meta">
            <div>APR 8, 2022</div>
            <div>&middot;</div>
            <div>David Labadze</div>
        </div>
        <div class="mt-4 post-preview loading-relaxed">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Possimus illo ad ullam nemo veritatis saepe voluptates reiciendis minus quidem alias, ab cupiditate dignissimos rem omnis perspiciatis beatae ut repudiandae maxime cum itaque repellat tempora laboriosam? Possimus sit nostrum repellat! Aliquid recusandae ut temporibus pariatur, amet ipsam iste, delectus, exercitationem eveniet sunt nostrum doloribus dolor? Voluptatem dolore facilis itaque quam corrupti quibusdam placeat fugiat, minus alias commodi? Alias deserunt non expedita fugit dolor labore, distinctio optio laborum dicta reiciendis pariatur perferendis quibusdam vitae vero quod omnis inventore placeat odit autem quis asperiores nostrum. Deleniti voluptates placeat earum tempora asperiores eligendi aspernatur!
        </div>
        <div class="mt-4">
            <NuxtLink :to="`/posts/1`" class="inline-block px-4 py-2 text-white bg-blue-700 rounded hover:bg-blue-800">
            Read More</NuxtLink>
        </div>
    </div>
</template>