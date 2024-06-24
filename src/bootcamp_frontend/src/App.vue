<script setup>
import { ref } from 'vue';
import { bootcamp_backend } from 'declarations/bootcamp_backend/index';
let greeting = ref('');

async function handleSubmit(e) {
  e.preventDefault();
  const target = e.target;
  const name = target.querySelector('#name').value;
  await bootcamp_backend.greet(name).then((response) => {
    greeting.value = response;
  });
}
</script>

<template>
  <main>
    <img src="/logo2.svg" alt="DFINITY logo" />
    Siema!
    <br />
    <button @click="podbij">podbij</button>
      {{ licznik }}
  </main>

  <script>
  export default {
    data() {
      return {
        licznik: 0
      }
    }
    methods: {
      podbij() {
        this.licznik++
      }
    }
  }
  </script>
</template>
