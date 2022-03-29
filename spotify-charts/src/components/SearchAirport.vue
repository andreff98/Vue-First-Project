<template>
  <div class="searchbox">
        <label>Airport: </label>
        <input v-model="airport" type="text" placeholder="Airport...">
        <button v-on:click="PesquisarAirport" :code="{airport}">Pesquisar</button>
        <p>{{airport}}</p>
    </div>
</template>

<script>
import { useRoute } from 'vue-router';
export default {
    data() {
        return {
            airport: "",
        }
    },
    methods: {
        PesquisarAirport: function(event) {
            // router.push({ name: 'user', params: { username } }) // -> /user/eduardo
            // router.push(`/user/${username}`)
            // this.$router.push(`/airport/${this.airport}`);
            // this.$router.push(`/airport/${this.airport}`);
            this.$router.push({name: 'airport', params: { code: 'SEA'}});
        }
    },
}
</script>

<style scoped>
.searchbox {
  margin-top: 1rem;
}

.searchbox label, .searchbox input, .searchbox button{
   margin-left: .5rem;
}

.searchbox label{
   color: hsla(160, 100%, 37%, 0.8);
}

.searchbox button{
  pad: .5rem 1rem;
  background: hsla(160, 100%, 37%, 1);
  color: white;
}

.searchbox button:hover{
  background-color: hsla(160, 100%, 37%, 0.2);
}
</style>