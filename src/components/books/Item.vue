<script setup>
import { defineProps, defineEmits } from "vue"

defineProps({
  book: {
    type: Object,
    required: true,
  },
})

const emits = defineEmits(["remove-book"])

const removeBook = (e) => {
  const btn = e.currentTarget
  const id = btn?.dataset.bookid
  if (id) {
    emits("remove-book", id)
  }
}
</script>

<template>
  <li class="flex items-center gap-2 text-2xl">
    <button :data-bookid="book.id" @click="removeBook" class="btn btn-square">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" /></svg>
    </button>
    <router-link :to="{ name: 'detail', params: { auo: book.id } }">
      {{ book.title }}
    </router-link>
  </li>
</template>
