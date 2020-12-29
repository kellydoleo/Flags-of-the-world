<template>
    <!-- <div class="nav" >




      <router-link to="/" >  <h1 id="logo" >Around the World</h1> </router-link>
        
            <i class="fas fa-moon right-align"></i>
            <button class="right-align" > Dark Mode</button>
        
    </div> -->

    <div>
  <b-navbar class="nav" toggleable="lg" type="light" variant="faded">
   <router-link to="/"> <b-navbar-brand >Around the World</b-navbar-brand></router-link>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
          <b-navbar-brand>
              <i class="fas fa-moon right-align"></i>
          </b-navbar-brand>
         <b-navbar-nav>
        
        <b-nav-item href="#">Dark Mode</b-nav-item>
        
      </b-navbar-nav>       

      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
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
    
    margin-left: -1%;
    margin-bottom: 3%;
    overflow: hidden;
    background-color: #ffffff;
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