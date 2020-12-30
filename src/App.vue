<template>
  <div  >
    <div >
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/show">About</router-link> -->
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return{
      mode: 'dark'
    }
  }
  
}
</script>

<style>
/* .app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #FAFAFA;
} */




/* .dark {
  background: hsl(207, 26%, 17%);
} */
</style>
