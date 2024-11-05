<script setup>
import { ref } from 'vue'
let missatge = ref('')

const emit = defineEmits(['enviarMissatge'])
const enviarMissatge = () => {
  if (missatge.value) {
    emit('enviarMissatge', missatge.value)
  }
  missatge.value = ''
}

const handleClick = (event) => {
  if (event.keyCode == 13) {
    enviarMissatge()
  }
}
</script>

<template>
  <div class="container">
    <div class="input">
      <input v-model="missatge" placeholder="Escriu el teu missatge..." @keydown="handleClick"/>
    </div>
    <div class="svg-container" @click="enviarMissatge" tabindex="1">
      <svg xmlns="http://www.w3.org/2000/svg" width="20px" height="20px" viewBox="0 0 24 24"><path fill="none" stroke="currentColor" stroke-width="2" d="M22 3L2 11l18.5 8zM10 20.5l3-4.5m2.5-6.5L9 14l.859 6.012c.078.546.216.537.306-.003L11 15z"/></svg>
    </div>
  </div>
</template>

<style scoped>
.container{
  display: flex;
  justify-content: space-between;
  width: 320px;
}
.svg-container{
  border: 1px solid #fff;
  border-radius: 9999px;
  width: 35px;
  height: 35px;
  display: flex;
  justify-content: center;
  align-items: center;

  &:hover{
    scale: 1.1;
  }
}
.input{
  border: 1px solid #fff;
  width: 300px;
  border-radius: 99px;
  background-color: #fff;
  input{
    margin-left: 10px;
    border: none;
    height: 100%;
    width: 250px;
    outline: none;
  }
}
</style>
