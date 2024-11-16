<template>
  <main class="flex flex-col justify-center p-7">
    <h1 class="text-3xl font-bold">Lista de usuarios</h1>
    <ul class="flex flex-wrap gap-3">
      <li 
        v-for="user in (users || [])" 
        :key="user.id"
        @click="handleClick(user)"
        class="grid px-3 py-3 transition-transform border cursor-pointer w-fit rounded-xl hover:scale-105"
      >
        <h3 class="text-xl font-bold">
          {{ user.name }}
        </h3>
        <p class="text-sm text-gray-500">
          {{ user.email }} - {{ user.phone }}
        </p>
      </li>
    </ul>

  </main>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  users: Array
})

const emit = defineEmits(['selectUser'])

const handleClick = (user) => {
  emit('selectUser', user)
}
</script>