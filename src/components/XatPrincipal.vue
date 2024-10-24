<script setup>
import { reactive } from 'vue'
import MissatgeComp from '@/components/MissatgeComp.vue'
const llistaMissatges = reactive([])
const gestionarRebuda = missatge => {
  llistaMissatges.push(missatge)
}
</script>

<template>
  <h1>Xat entre usuaris</h1>
  <ul>
    <li v-for="(missatge, index) in llistaMissatges" :key="index">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="1em"
        height="1em"
        viewBox="0 0 20 20"
      >
        <path
          fill="currentColor"
          d="M9.993 10.573a4.5 4.5 0 1 0 0-9a4.5 4.5 0 0 0 0 9M10 0a6 6 0 0 1 3.04 11.174c3.688 1.11 6.458 4.218 6.955 8.078c.047.367-.226.7-.61.745c-.383.045-.733-.215-.78-.582c-.54-4.19-4.169-7.345-8.57-7.345c-4.425 0-8.101 3.161-8.64 7.345c-.047.367-.397.627-.78.582c-.384-.045-.657-.378-.61-.745c.496-3.844 3.281-6.948 6.975-8.068A6 6 0 0 1 10 0"
        />
      </svg>
      <span>Usuari 1:</span><br />
      {{ missatge }}
    </li>
  </ul>
  <MissatgeComp @enviarMissatge="gestionarRebuda" />
</template>

<style scoped>
ul {
  margin: 0;
  padding: 0;
  height: auto;
  max-height: 400px;
  overflow-y: auto;
  scroll-behavior: smooth;
}

li {
  background-color: #333;
  width: 300px;
  list-style: none;
  height: 50px;
  border-radius: 5px;
  margin: 10px;
}

span {
  color: rgb(255, 153, 0);
  font-weight: bold;
}
</style>
