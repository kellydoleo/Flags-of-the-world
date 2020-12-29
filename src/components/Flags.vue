<template>
    <div id="get-flags" >
        
         
         <div v-bind:key="flag" v-for="flag in flags">
        <router-link :to="{ name: 'Show', params: {name : flag.name}}" > <img :src="flag.flag"/> </router-link>
             <div>
             <h3>{{flag.name}}</h3>
             <p>Population: {{flag.population}}</p>
             <p>Region: {{flag.region}}</p>
             <p>Capital: {{flag.capital}}</p>
             </div>

         </div>
       
    </div>

    
</template>

<script>
import axios from 'axios';

export default {
    name: "Flags",
    data() {
        return {
            flags: []

        }

    },
    methods: {

    },
    created() {
        axios.get('https://restcountries.eu/rest/v2/all')
        .then(res => this.flags = res.data)
        .catch(err => console.log(err))
    }
   
    
}
</script>

<style scoped>

</style>