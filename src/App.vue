  <script setup>
  import { ref, onMounted } from 'vue'

  const contador = ref(0)

  const nome = 'Theodoro'
  const idade = 16

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

  function invertermaisculo(texto) {
        return texto.split('').reverse().join('').toUpperCase('')
    }

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }

  onMounted(() => {
    console.log(`O valor inicial do contador é ${contador.value}.`)
  })  
  </script>

  <template>
    <div class="info">
    <button @click="incrementarContador">Mais</button>
    <button @click="decrementarContador">Menos</button>
    <button @click="resetar">reset</button>
    <p class="contador">Valor do contador é: {{ contador }}</p>
    <div class="maior" v-if="contador > 10"><p>O numero é maior que 10</p></div>
    <div class="menor" v-else-if="contador < 10"> O numero é menor que 10</div>
    <div class="dez" v-else>O numero é 10</div>
    </div>

    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ invertermaisculo(nome) }} </p>
        <p>O nome invertido é: {{ inverter(nome) }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
  </template>

  <style scoped>
  .contador {
    border: 3px solid gray;
    border-radius: 10px;
    background-color: black;
    color: white;
    margin: 10px;
  }
  button {
    font-weight: bold;
    background-color: black;
    border: 3px solid gray;
    border-radius: 10px;
    color: white;
    margin: 10px 50px;
  }

  .maior {
    border: 3px solid gray;
    border-radius: 10px;
    background-color: green;
    color: black;
    margin: 10px 10px 10px 10px;
  }

  .menor {
    border: 3px solid gray;
    border-radius: 10px;
    background-color: red;
    color: black;
    margin: 10px 10px 10px 10px;
  }

  .dez {
    border: 3px solid gray;
    border-radius: 10px;
    background-color: yellow;
    color: black;
    margin: 10px 10px 10px 10px;
  }
  
  .info {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
  margin: 30px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
  </style>