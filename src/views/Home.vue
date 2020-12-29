<template>
  <div id="app" >
    <div>
      
      <Header />
      <Flags />

    </div>
    
    
  </div>
</template>

<script>
import Flags from '../components/Flags'
import Header from '../components/layout/Header'


export default {
  name: 'App',
  components: {
    Flags,
    Header
    
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
