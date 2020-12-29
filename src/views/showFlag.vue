<template>
    <div>
        <Header />

    <!-- <div v-bind:key="flag" v-for="flag in flags" >
       <h1> {{flag[0].name}}</h1> -->
    <!-- </div>  -->

    </div>
</template>

<script>
import Header from '../components/layout/Header'
// import axios from 'axios'



export default {
    name: "showFlag",
    // data() {
    //     // flags: []
    // },
    
   
    components: {
        Header,
       
    },
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
    
    

    
    
    
}
</script>

<style scoped>

</style>