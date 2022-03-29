<template>
  <div>
      <p>{{ airport.name }} ({{ airport.abbreviation }})</p>
      <p>Located in {{ airport.city }}, {{airport.state}}</p>
  </div>
</template>

<script>
import airports from '@/data/airports.js';
import { computed } from 'vue';
import { useRoute } from 'vue-router';

export default {
    setup(){
        const route = useRoute() //Usar o route (url)
            const airport = computed(() => { // Obeter o :code do url
                return airports.filter(a => a.abbreviation === route.params.code.toUpperCase())[0] //Retornar o primeiro resultado que encontra
            })

            return {airport}
    }
}
</script>

<style>

</style>