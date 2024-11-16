<template>
  <div class="grid p-4 text-center border rounded-xl place-content-center w-fit">
    <h1 class="text-3xl font-bold">User information</h1>
    <h3>Nombre: {{ user.name }}</h3>
    <p>UserName: {{ user.username }}</p>
    <p>Email: {{ user.email }}</p>
    <p>Telefono: {{ user.phone }}</p>
    <p>Pagina Web: {{ user.website }}</p>
    <p>Direccion: {{ user.address?.street }}, {{ user.address?.city }}</p>
  </div>
</template>

<script setup>
  import { defineProps } from 'vue';

  const props = defineProps({
    user : {
      type: Object,
      required: true
    }
  })
</script>