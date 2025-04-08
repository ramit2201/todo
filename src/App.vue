<script setup>
import ToDo from './components/ToDo.vue'
</script>

<template>
  <main>
    <ToDo />
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;  /* Center horizontally */
  align-items: center;      /* Center vertically */
  height: 100vh;            /* Full viewport height */

}
</style>
