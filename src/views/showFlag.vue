<template>
    <div>
        <Header />

       <img :src="flags[0].flag" /> 
       <div>
       <h1 > {{flags[0].name}}</h1>
       <p>Native Name: {{flags[0].nativeName}}</p>
       <p>Population: {{flags[0].population}}</p>
       <p>Region: {{flags[0].region}}</p>
       <p>Sub. Region: {{flags[0].subregion}}</p>
       <p>Capital: {{flags[0].capital}}</p>
       <p>Top Level Domain: {{flags[0].topLevelDomain[0]}}</p>
       <p>Currencies: {{flags[0].currencies[0].name}}</p>
       <p>Language(s): {{flags[0].languages[0].name}}</p>

       
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
            flags: []
        }
    },
    
   
    components: {
        Header,
       
    },
    computed: {
        
         

    },
    created() {
        axios.get(`https://restcountries.eu/rest/v2/name/${this.$route.params.name}?fullText=true`)
        .then(res => this.flags = res.data)
        .catch(err => console.log(err))
    },
    methods: {
        // oneFlag() {
        //        axios.get(`https://restcountries.eu/rest/v2/name/${name}?fullText=true`)
        //       .then(this.flags = this.flags.filter(flag => this.$route.params.name == name) )
        //       .catch(err => console.log(err))
                   
        //        }
               
           }
        
    }

   
    // created() {
    //     axios.get('https://restcountries.eu/rest/v2/all')
    //     .then(res => this.flags = res.data)
    //     .catch(err => console.log(err))
    // },
    //  computed: {

    //      oneFlag() {
    //         if(this.flags.name == name) {
    //             return this.flags.filter((flag) => {
    //                 return this.flag[0]
    //             })
    //         } else {
    //             return this.flags
    //         }
    //     },
    //     methods: {
    //         oneFlag() {
    //            axios.get(`https://restcountries.eu/rest/v2/name/${name}?fullText=true`)
    //            .then(this.flags = this.flags.filter(flag => {
    //                if(flag.name == name){
    //                    return this.flags
    //                }
    //            } ))
               
    //        }

    //     }
        

    

    // methods: {
    //     getCurrentFlag(name) {
    //         flag.get(name)
    //         .then(res => this.currentFlag = res.data)
    //     }
    
    

    
    
    

</script>

<style scoped>

</style>