<template>
    <div>
        <Header />
        <h1 >{{flags.name}}</h1>
      

    </div>
</template>

<script>
import Header from '../components/layout/Header'



export default {
    name: "showFlag",
    
   
    components: {
        Header,
       
    },
    props: ["flags"]

    // methods: {
    //     getCurrentFlag(name) {
    //         flag.get(name)
    //         .then(res => this.currentFlag = res.data)
    //     }
    
    

    
    
    
}
</script>

<style scoped>

</style>