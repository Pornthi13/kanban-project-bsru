<template>
  <div id="app">
   <Kanban :data = "data"/>
  </div>
</template>

<script>
import Kanban from "./components/Kanban"


export default {
  name: 'App',
  components: {
   Kanban
  },
  data(){
    return{
      data:[
        {
          name:"todo",
          colors:"#FF3333",
          tasks:[]
        },
        {
          name:"doing",
          colors:"#CC00FF",
          tasks:[]
        },
        {
          name:"done",
          colors:"#6666FF",
          tasks:[]
        }
      ]
    }
  }
}
</script>

<style>
#app {
  height:100vh ;
}
</style>
