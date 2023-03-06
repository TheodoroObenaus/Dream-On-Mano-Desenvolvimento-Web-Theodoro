  <script setup>
  import { ref, onMounted } from 'vue'

  const contador = ref(0)

  function incrementarContador() {
  contador.value++
  }
  function decrementarContador() {
    if (contador.value > 0) {
    contador.value--
    }
  }

  function resetar() {

  contador.value = 0
  }

  onMounted(() => {
    console.log(`O valor inicial do contador é ${contador.value}.`)
  })
  </script>

  <template>
    <button @click="incrementarContador">Mais</button>
    <button @click="decrementarContador">Menos</button>
    <button @click="resetar">reset</button>
    <p>Valor do contador é: {{ contador }}</p>
  </template>

  <style scoped>
  p {
    border: 3px solid gray;
    border-radius: 10px;
    background-color: black;
    color: white;
    margin: 10px 10px 10px 10px;
  }
  button {
    font-weight: bold;
    background-color: black;
    border: 3px solid gray;
    border-radius: 10px;
    color: white;
    margin: 10px 10px 10px 10px;
  } 
  </style>