<template>
  
  <Navbar/>
 
  <SideItems/>
  <Centerbar/>
  
</template>

<script>

import Navbar from './components/Navbar.vue'

import SideItems from './components/SideItems.vue' 
import Centerbar from './components/Centerbar.vue'


export default {
  name: 'App',
  components: { 
    
    
    Navbar,
   SideItems,
   Centerbar
    
  }
}
</script>


