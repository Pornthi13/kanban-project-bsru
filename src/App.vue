<template>
  <div id="app">
   <Kanban :data = "data" :cerate_task_submit="cerate_task_submit"/>
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
          colors:"#CC00FF",
          tasks:[{
            task_name:"task"
          }]
        },
        {
          name:"doing",
          colors:"#FF6699",
          tasks:[{
            task_name:"task"
          }]
        },
        {
          name:"done",
          colors:"#6666FF",
          tasks:[{
            task_name:"task"
          }]
        }
      ]
    }
  },
  methods:{
    cerate_task_submit(column_index,item){
      this.data[column_index].tasks.push(item)
    }
  }
}
</script>

<style>
#app {
  height:100vh ;
}
</style>
