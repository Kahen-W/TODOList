<script setup>
import { ref, defineEmits } from "vue"

const bookName = ref("")

const emits = defineEmits(["add-book"])

const addBook = () => {
  emits("add-book", bookName.value)
  bookName.value = ""
}
</script>

<template>
  <div class="flex items-center gap-2 mt-4">
    <input
      v-model.trim="bookName"
      @keydown.enter="addBook"
      type="text"
      class="w-full input input-bordered"
    />
    <button @click="addBook" class="text-white bg-gradient-to-r from-cyan-500 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-cyan-300 dark:focus:ring-cyan-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2">Add</button>
  </div>
</template>
