<template>
  <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined" rel="stylesheet" />
  <body>
    <ul class="sidebar">
    
    <li v-for="item in data" :key="item.id">
      
      <h1 v-on:click="item.show = !item.show" >
         {{item.name}}
        <span class="material-symbols-outlined">arrow_drop_down</span>
      </h1>
    <ul class="side-menu">

      <ul v-if="item.show">
        <li v-for="children in item.children" :key="children">
          <h1 v-on:click="children.show = !children.show">
            {{children.name}}
            
          </h1>
          <ul class="side-items">
          <ul v-if="children.show">
            <li v-for="children in children.next" :key="children">
              <h1>
                {{children.name}}
                
              </h1>
            
            </li>
            
          </ul>
          </ul>
        </li>
        </ul>
      </ul>
    </li>
  </ul>
   
  </body>
</template>
<script>
import jsonData from '/src/jsonData.json'
export default{
  data(){
    return{
     data:jsonData
    }
  }
}
</script>
<style scoped>
.sidebar{
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
  margin-top:20px;
  font-size: 14px;
  margin-left: 70px; 
  color:gray;
  position:relative;
  padding:5px;
}


.side-menu{
  margin-left: 10px; 
  color: black;
  padding: 5px;
 }
.side-menu h1{
  font-weight:bold;
  padding: 5px;
  }
.side-menu h1:hover{
  background-color: transparent;
  color: #276cda;
}
.side-items{
  margin-left: 30px; 
  }
</style>
