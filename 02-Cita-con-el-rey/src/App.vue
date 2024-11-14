<template>
  <div class="card">
    <div class="text">
      <h2>Cena {{ actualRey+1 }} con el rey golo <span class="name">{{ rey }}</span></h2>
      <p>
        Precio: <span class="price">${{ reyes[actualRey].precio }}</span>
      </p>
      <p v-if="reyes[actualRey].finDeSemana" class="days weekend">Fines de Semana</p>
      <p v-else class="days">Lunes a Viernes</p>
      <div class="discount" v-show="reyes[actualRey].precio < 100">
        <p>Ahora un 10% dto: <span>${{ discount }}</span> </p>
        <img src="../public/oferta.jpg" alt="">
      </div>
      <img :src="imgRey" alt="">
    </div>
    <button @click="increment">Siguiente ({{ actualRey+1 }}/{{ total }})</button>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import { reyes } from './products';

const actualRey = ref(0)
const total = reyes.length

const increment = () => {
  actualRey.value++
  if (actualRey.value >= total) {
    actualRey.value = 0
  }
}

const rey = computed(() => {
  const nombre = reyes[actualRey.value].nombre.toLowerCase()
  return nombre.substring(0,1).toUpperCase() + nombre.substring(1)
})

const imgRey = computed(() => {
  return `https://www.html6.es/img/rey_${reyes[actualRey.value].nombre.toLowerCase()}.png`
})

const discount = computed ( () => {
  return Number(reyes[actualRey.value].precio/1.10).toFixed(2)
})

</script>

<style scoped>
/* Estilos generales */
.card {
  display: grid;
  place-items: center;
  width: 500px;
  min-height: 800px;
  padding: 20px 0;
  border: 1px solid #ddd;
  border-radius: 15px;
  background-color: #f9f9f9;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

/* Texto principal */
.text {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: Arial, sans-serif;
}

.text h2 {
  font-size: 1.5rem;
  color: #333;
}

.name {
  color: #28a745;
  font-weight: bold;
  font-size: 1.75rem;
}

/* Indicador de días */
.days {
  background: #28a745;
  color: white;
  padding: 5px 15px;
  border-radius: 10px;
  font-weight: bold;
}

.weekend {
  background: #ff4d4d;
}

/* Precio y descuento */
.price {
  font-size: 1.5rem;
  color: #28a745;
  font-weight: bold;
}

.discount {
  display: flex;
  align-items: center;
  gap: 5px;
  color: #333;
}

.discount span {
  font-size: 1.2rem;
  color: #28a745;
  font-weight: bold;
}

.discount img {
  height: 20px;
}

/* Botón */
button {
  font-size: 1.2rem;
  padding: 10px 20px;
  border-radius: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s;
  grid-row: 3;
}

button:hover {
  background-color: #0056b3;
}

</style>

