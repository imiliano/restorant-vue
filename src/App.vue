<script setup>
import { ref, onMounted } from 'vue';
import { db } from './data/comidas';
import Comida from './components/Comida.vue';
import Header from './components/Header.vue';

const comidas = ref([]);

onMounted(()=>{
  comidas.value = db;
})

const incrementar = (c) =>{
  console.log(c);
}
</script>

<template>

  <Header />

<div class="container-xl">
  <div class="row">

<Comida 
v-for="comida in comidas"
:comida="comida"
@incrementar-carrito="incrementar"
/>

  </div>
</div>
    
</template>
