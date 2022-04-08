<template>
  <div class="container w-1/2 py-8 mx-auto">
    <ul
      v-if="errors.length > 0"
      className="mb-4 list-disc list-inside text-sm text-red-600"
    >
      <li v-for="(error, index) in errors" :key="index">
        {{ error }}
      </li>
    </ul>
    <form action="#" class="space-y-6" @submit.prevent="createPost">
      <div>
        <label for="title" class="block font-semibold">Title</label>
        <input
          type="text"
          v-model="title"
          id="title"
          class="w-full px-2 py-2 mt-2 rounded shadow"
        />
      </div>
      <div>
        <label for="body" class="block font-semibold">Body</label>
        <textarea
          v-model="body"
          name="body"
          id="body"
          cols="30"
          rows="10"
          class="w-full px-2 py-2 mt-2 rounded shadow"
        ></textarea>
      </div>
      <div>
        <button
          type="submit"
          class="inline-block px-4 py-2 text-white bg-blue-600 rounded hover:bg-blue-700"
        >
          Create Post
        </button>
        <span v-show="isLoading">Loading...</span>
      </div>
    </form>
  </div>
</template>

<script setup>
definePageMeta({
  middleware: ['auth'],
})
const title = ref('')
const body = ref('')
const isLoading = ref(false)
const errors = ref([])
const router = useRouter()

async function createPost() {
  isLoading.value = true
  try {
    const post = await useNuxtApp().$apiFetch(`/api/post`, {
      method: 'POST',
      body: {
        title: title.value,
        body: body.value,
      },
    })

    isLoading.value = false

    title.value = ''
    body.value = ''

    alert('creating post')

    router.push('/')
  } catch (err) {
    console.log(err.data)
    errors.value = Object.values(err.data.errors).flat()
    isLoading.value = false
  }
}
</script>
