<script setup>
import { ref, onMounted } from 'vue'

const contador = ref(0)

function incrementarContador() {
  this.contador.value++
}
function decrementarContador() {
  if (this.contador > 0) {
  this.contador.value--
  }
}

onMounted(() => {
  console.log(`O valor inicial do contador é ${contador.value}.`)
})
</script>

<template>
  <button @click="incrementarContador">Mais</button>
  <button @click="decrementarContador">Menos</button>
  <p>Valor do contador é: {{ contador }}</p>
</template>

<style scoped>
p {
  border: 3px solid gray;
  border-radius: 10px;
  background-color: black;
  color: white;
}
button {
  font-weight: bold;
  background-color: black;
  border: 3px solid gray;
  border-radius: 10px;
  color: white;
} 
</style>