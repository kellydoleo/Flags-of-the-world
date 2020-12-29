<template>
  <div id="app" >
    <div>
      
      <Header />
      <!-- <SearchBar v-bind:flag="flags" /> -->
      <Flags />

    </div>
    
    
  </div>
</template>

<script>
import Flags from '../components/Flags'
import Header from '../components/layout/Header'
// import SearchBar from '../components/SearchBar'


export default {
  name: 'App',
  components: {
    Flags,
    Header,
    // SearchBar
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
