<template>
    <div id="get-flags" >
         <input type="text" v-model="searchQuery" placeholder="Search..." />
         
         <div v-bind:key="flag" v-for="flag in resultQuery">
            <router-link :to="{ name: 'Show', params: {name : flag.name}}" > <img :src="flag.flag"/> </router-link>
             <div>
             <h3>{{flag.name}}</h3>
             <p>Population: {{flag.population}}</p>
             <p>Region: {{flag.region}}</p>
             <p>Capital: {{flag.capital}}</p>
             </div>

         </div>

         <ShowFlag v-bind:flag="flags" />

    </div>

    
</template>

<script>
import axios from 'axios';
import ShowFlag from '../views/showFlag'


export default {
    name: "Flags",
    components: {
        ShowFlag
    },
    data() {
        return {
            searchQuery: null,
            flags: []

        }

    },
    methods: {

    },
    created() {
        axios.get('https://restcountries.eu/rest/v2/all')
        .then(res => this.flags = res.data)
        .catch(err => console.log(err))
    },
    computed: {
        resultQuery() {
            if(this.searchQuery) {
                return this.flags.filter((flag) => {
                    return this.searchQuery.toLowerCase().split(' ').every(v => flag.name.toLowerCase().includes(v))
                })
            } else {
                return this.flags
            }
        }
    }
   
    
}
</script>

<style scoped>

</style>