<template>
  <div v-if="airport">
      <p>{{ airport.name }} ({{ airport.abbreviation }})</p>
      <p>Located in {{ airport.city }}, {{airport.state}}</p>
  </div>
  <div v-else>
        <h1>404 - Page not found!</h1>
        <p>Esta página já não existe ou mudou de localização</p>
  </div>
</template>

<script>
import airports from '@/data/airports.js';
import { computed } from 'vue';
import { useRoute } from 'vue-router';

export default {
    setup(){
        const route = useRoute() //Usar o route (url)
            const airport = computed(() => { // Obter o :code do url
                return airports.filter(a => a.abbreviation === route.params.code.toUpperCase())[0] //Retornar o primeiro resultado que encontra
            })

            return {airport}
    },
}
</script>

<style>

</style>