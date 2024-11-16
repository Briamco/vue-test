<template>
  <main class="flex flex-col justify-center p-7">
    <h1 class="text-3xl font-bold">Lista de usuarios</h1>
    <ul class="flex flex-wrap gap-3">
      <li 
        v-for="user in users" 
        :key="user.id"
        @:click="selectUser(user)"
        class="grid px-3 py-3 transition-transform border w-fit rounded-xl hover:scale-105"
      >
        <h3 class="text-xl font-bold">
          {{ user.name }}
        </h3>
        <p class="text-sm text-gray-500">
          {{ user.email }} - {{ user.phone }}
        </p>
      </li>
    </ul>

    <userDetail v-if="selectedUser" :user="selectedUser" />
  </main>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import userDetail from './userDetail.vue'

const users = ref([])
const selectedUser = ref(null)

const selectUser = (user) => {
  selectedUser.value = user
}

onMounted(() => {
  fetch('https://jsonplaceholder.typicode.com/users')
    .then(res => res.json())
    .then(json => users.value = json)
})

</script>