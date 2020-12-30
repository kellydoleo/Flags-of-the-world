<template>
    <div>
        <Header v-on:toggle= "toggle" v-bind:mode="mode"/>
        <b-button id="back-button" href="/" > ← Back</b-button>
       <div class="flag-container" :class="mode"  > 
        <img :src="flags[0].flag" /> 
        <div class="demo-info-details" :class="mode" >
            <h1 > {{flags[0].name}}</h1>
            <p>Native Name: {{flags[0].nativeName}}</p>
            <p>Population: {{flags[0].population}}</p>
            <p>Region: {{flags[0].region}}</p>
            <p>Sub. Region: {{flags[0].subregion}}</p>
            <p>Capital: {{flags[0].capital}}</p>
            <p>Top Level Domain: {{flags[0].topLevelDomain[0]}}</p>
            <p>Currencies: {{flags[0].currencies[0].name}}</p>
            <p>Language(s): {{flags[0].languages.map(language=>language.name)}}</p>
        </div>
    </div>
    </div>
</template>

<script>
import Header from '../components/layout/Header'
import axios from 'axios'



export default {
    name: "showFlag",
    data() {
        return {
            flags: [],
            mode: 'light'
        }
    },
    
    components: {
        Header,
       
    },
    methods: {
        toggle() {
      if (this.mode === "dark") {
        this.mode = "light"
      } else (this.mode = 'dark')
    }

    },
    
   
    created() {
        axios.get(`https://restcountries.eu/rest/v2/name/${this.$route.params.name}?fullText=true`)
        .then(res => this.flags = res.data)
        .catch(err => console.log(err))
    }
    }

   
    
    
    

</script>

<style scoped>
.flag-container {
    display:flex;
    flex-wrap: wrap;

}

.demo-info-details {
    margin-left: 7%;
    margin-top: 6%;
}

img {
    max-width: 41%;
    margin-left: 5%;
    margin-top: 5%;
    margin-bottom: 5%;
}

#back-button {
    display: flex;
    flex-direction: column;
    margin-left: 5%;
    margin-bottom: -1%;
    width: 9%;
    background: #FFFFFF;
    border: 5px solid #FFFFFF;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.13);
    color: black;

}

</style>