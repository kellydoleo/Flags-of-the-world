<template>
    <!-- <div class="nav" >




      <router-link to="/" >  <h1 id="logo" >Around the World</h1> </router-link>
        
            <i class="fas fa-moon right-align"></i>
            <button class="right-align" > Dark Mode</button>
        
    </div> -->

    <div id="header" >
  <b-navbar class="nav" :class='mode' toggleable="lg" type="light" variant="faded">
   <router-link  to="/"> <b-navbar-brand  >Around the World</b-navbar-brand></router-link>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
          <b-navbar-brand>
              <i class="fas fa-moon right-align"></i>
          </b-navbar-brand>
         <b-navbar-nav>
        
        <button 
        
        id="mode-button" 
        :clicked="(mode === 'dark') ? 'clicked' : false"  
        @click ="$emit('toggle')"
        >{{mode}} Mode</button>
        
      </b-navbar-nav>       

      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<script>

export default {
    name: 'Header',
    props: ['mode']
}
</script>

<style>

.nav {
    display: flex;
    flex-direction: flex-start;
    align-items: flex-start;
    padding: 10px;
    box-shadow: 0px 4px 4px rgba(0,0,0,0.08);
    margin-left: -1%;
    margin-bottom: 5%;
    overflow: hidden;
    background-color: #ffffff;
}

.nav > a  {
    text-decoration: none;
    padding-left: 15px;
   
    
}

#mode-button {
    text-transform: capitalize;
    background-color: #ffffff;
    box-shadow: 0px 4px 4px rgba(0,0,0,0.08);
    
    border: white;
    
}

.nav > svg {
    position: relative;
    background-color: hsl(209, 23%, 22%);

    

}

.dark #mode-button {
    background: hsl(209, 23%, 22%);
    color: hsl(0, 0, 100%);
}

.dark .

.dark .nav {
 background: hsl(209, 23%, 22%);
 
 
}

.dark a {
    color: hsl(0, 0, 100%);
}

.right-align {
    /* display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 10px; */
    float: right;
}

/* .light-theme-elements-text {
    background-color: #FFFFFF;
    color: hsl(100, 15%, 8%);
} */

/* .light-theme-html-background {
    background-color: #FAFAFA;
}

.light-theme-search {
    color: hsl(0, 0%, 52%);
    background-color: #FFFFFF;
}

.dark-theme-search {
    color: hsl(0, 0%, 52%);
    background-color: #FFFFFF;
}

.dark-theme-elements-text {
    background-color: hsl(209, 23%, 22%);
    color: hsl(0, 0, 100%);
}

.dark-theme-html-background {
    background-color: hsl(207, 26%, 17%);
} */

</style>