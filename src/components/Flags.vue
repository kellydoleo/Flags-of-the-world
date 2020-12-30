<template>
    <div id="get-flags" >
         <input class="search-bar" :class='mode' type="text" v-model="searchQuery" placeholder="Search..." />
         <div class="holding-flags">
         <div class="flags" v-bind:key="flag" v-for="flag in resultQuery">
            <router-link :to="{ name: 'Show', params: {name : flag.name}}" > <img :src="flag.flag"/> </router-link>
             <div class="demo-info" :class='mode'>
             <h3>{{flag.name}}</h3>
             <p>Population: {{flag.population}}</p>
             <p>Region: {{flag.region}}</p>
             <p>Capital: {{flag.capital}}</p>
             </div>
        </div>
         </div>

         <!-- <ShowFlag v-bind:flag="flags" v-on:one-flag="oneFlag" /> -->

    </div>

    
</template>

<script>
import axios from 'axios';
// import ShowFlag from '../views/showFlag'


export default {
    name: "Flags",
    components: {
        // ShowFlag
    },
    props: ['mode'],
    data() {
        return {
            searchQuery: null,
            flags: []

        }

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

img {
 max-width: 80%;
 
 
 
}

input {
    margin-bottom: 5%;
}




.holding-flags {
    display: flex;
    flex-wrap: wrap;
    
}

.flags {
    max-width: 25%;
    
    
}

.search-bar {
    background: #FFFFFF;
    border: 5px solid #FFFFFF;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.13);
    width: 25%;
    display: inline;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 10px;
    margin-left: 1%;
    margin-top: 3%;
    
}

.demo-info {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 5px;
    background: #FFFFFF;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.11);
    max-width: 75%;
    margin-left: auto;
    margin-right: auto;
    
   
}

p {
    margin: 3px;
}

.dark .demo-info {
    background: hsl(209, 23%, 22%);
}

.dark .search-bar {
    background: hsl(209, 23%, 22%);
    border: 5px solid hsl(209, 23%, 22%);
}


</style>