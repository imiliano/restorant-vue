<script setup>
const props = defineProps({
    comida:{
        type:Object,
        required: true
    }
})

defineEmits(['incrementar-carrito'])

</script>

<template>
   
<div class="col-md-4 col-lg-3 col-sm-6 text-center text-warning my-5 fw-bold">
    <img v-bind:src="'/' + comida.imagen + '.jpg'" alt="imagen de comida" class="img-fluid rounded">
    <h3 class="text-uppercase">{{ comida.nombre }}</h3>
    <small class="my-1">{{ comida.descripcion }}</small>
    <p class="my-1">${{ comida.precio }}</p>
      <button
      type="button"
      class="btn btn-outline-warning border border-secondary fw-bold"
      @click="$emit('incrementar-carrito', comida)"
      >
      Agregar al carrito
    </button>
</div>
</template>