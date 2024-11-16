<template>
  <div v-if="!showList" class="flex items-center justify-center h-screen font-bold text-8xl">Loading...</div>
  <div v-if="error" class="grid place-items-center">{{ error }}</div>
  <div class="grid place-items-center" v-if="showList">
    <userList :users="users" @selectUser="selectUser"/>
    <userDetail :user="selectedUser" v-if="selectedUser"/>
  </div>
</template>

<script setup>
import userList from './components/userList.vue'
import userDetail from './components/userDetail.vue';
import { ref, onMounted } from 'vue'

const users = ref([])
const selectedUser = ref(null)
const showList = ref(false)
const error = ref(null)

const selectUser = (user) => {
  selectedUser.value = user
  console.log(selectedUser);
}

const fetchUsers = async () => {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    const json = await res.json()
    users.value = json
    showList.value = true
  } catch (e) {
    error.value = 'Error al conectar con la API'
  }
}

onMounted(fetchUsers)
</script>