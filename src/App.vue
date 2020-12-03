<template>
  <div id="app">
    <Kanban :data="data" :cerate_task_submit="cerate_task_submit" :move_item_task="move_item_task" />
  </div>
</template>

<script>
import Kanban from "./components/Kanban";

export default {
  name: "App",
  components: {
    Kanban,
  },
  data() {
    return {
      data: [
        {
          name: "todo",
          colors: "#CC00FF",
          tasks: [
            {
              task_name: "task",
            },
          ],
        },
        {
          name: "doing",
          colors: "#FF6699",
          tasks: [
            {
              task_name: "task",
            },
          ],
        },
        {
          name: "done",
          colors: "#6666FF",
          tasks: [
            {
              task_name: "task",
            },
          ],
        },
      ],
    };
  },
  methods: {
    cerate_task_submit(column_index, item) {
      this.data[column_index].tasks.push(item);
    },
    move_item_task(column_a, index_task_a, column_b, index_task_b) {
      var item = this.data[column_a].tasks[index_task_a];
      // remove task brfor
      this.data[column_a].tasks.splice(index_task_a, 1);

      //move to
      this.data[column_b].tasks.splice(index_task_b, 0, item);
    },
  },
};
</script>

<style>
#app {
  height: 100vh;
}
</style>
