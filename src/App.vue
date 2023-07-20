<script setup>
import { ref } from 'vue'

const msg = ref("Info Pendaftaran Barudak well");
let rawHtml = "<li> Punya Spokat Nyala</li> <li>Jaket Gelembung</li> <li> Ripped Jeans</li> "
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
};
let seen = " "

let a = 10
let b = 5
let c = a+b
</script>
<template>

<form @submit.prevent="onSubmit">
  <div>
    <h1>{{ msg }} </h1>
    <div v-bind="objectofAttrs">Ketentuan masuk:</div>
    <span v-html="rawHtml"></span>
    <p v-if="seen">minimal harus bikin jj pake tongkat baseball</p>
  <button :disabled="isButtonDisabled">Button</button>&ensp;    
  <button :disabled="isButtonDisabled">Button</button>

  <h1>ARITMATIKA</h1>
  bil={{ a }} bil={{ b }}<br> hasil bil1 {{ a }} + bil2 {{ b }}= {{ c }}
  
  </div>
  </form>
</template>