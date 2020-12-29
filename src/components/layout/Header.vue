<template>
    <div class="nav" >
      <router-link to="/" >  <h1 id="logo" >Around the World</h1> </router-link>
        
            <i class="fas fa-moon right-align"></i>
            <button class="right-align" > Dark Mode</button>
        
    </div>
</template>

<script>

export default {
    name: 'Header'
}
</script>

<style scoped>
.nav {
    display: flex;
    flex-direction: flex-start;
    align-items: flex-start;
    padding: 10px;
    box-shadow: 0px 4px 4px rgba(0,0,0,0.08);
    width: 100%;
    margin-left: -1%;
    margin-bottom: 5%;
    overflow: hidden;
}

.nav > a  {
    text-decoration: none;
    color: #111517;
    padding-left: 15px;
   
    
}

.nav > svg {
    position: relative;

    

}

.right-align {
    /* display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 10px; */
    float: right;
}

</style>