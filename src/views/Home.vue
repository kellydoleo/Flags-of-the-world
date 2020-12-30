<template>
  <div class="app" :class= 'mode' >
    <div>
      
      <Header v-bind:mode="mode" v-on:toggle= "toggle" />
      <!-- <SearchBar v-bind:flag="flags" /> -->
      <Flags v-bind:mode="mode" />

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
    
    
  },
  data() {
    return {
      mode: 'light'
    }
  },
  methods: {
    toggle() {
      if (this.mode === "dark") {
        this.mode = "light"
      } else (this.mode = 'dark')
    }

  }
  
}
</script>

<style>
.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #FAFAFA;
  color: #111517;
 
  
}

.app > a {
  color: #111517;

}

.dark {
  background: hsl(207, 26%, 17%);
  color: #FAFAFA;
}

.dark > a {
  color: #FAFAFA;
}
</style>
