<template>
  <div class="wrapper">
    <h2 class="title">Draggable example</h2>
    <button @click="sort">
      To original order
    </button>
    <draggable v-model="taskList" class="bigger-area">
      <transition-group name="list-complete">
        <div
          v-for="task in taskList"
          :key="task.id"
          class="drag-item flex flex-justify-betweeen"
        >
          <strong>[IT-{{ task.id }}]</strong> {{ task.content }}
        </div>
      </transition-group>
    </draggable>
  </div>
</template>

<script>
import draggable from "vuedraggable";
import { taskList } from "../initialTasks";

export default {
  name: "Drag",
  data() {
    return {
      exampleList: ["Item 1", "Item 2", "Item 3", "Item 4", "Item 5"],
      taskList,
      originalTaskList: taskList
    };
  },
  components: {
    draggable
  },
  methods: {
    log: function(...e) {
      console.log(...e);
    },
    sort() {
      this.taskList = this.originalTaskList;
      // console.log(this.taskList);
    }
  }
  // watch: {
  //   taskList: function(newList, oldList) {
  //     console.log(newList);
  //     console.log(oldList);
  //   }
  // }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wrapper {
  width: auto;
  /* margin: 0 auto; */
  height: auto;
}
/* 
.row {
  display: flex;
  width: 100vw;
}

.row-data {
  width: 300px;
  background: #ccc;
} */

.title {
  margin-bottom: 2em;
}

.bigger-area > span {
  /* min-height: 90vh; */
  /* display: block; */
}
.drag-item {
  padding: 15px 10px;
  background-color: whitesmoke;
  min-width: 30vw;
  max-width: 90vw;
  margin: 0 auto 10px;
  cursor: -moz-grab;
  cursor: -webkit-grab;
  cursor: grab;
  transition: transform 0.25s cubic-bezier(0.02, 1.01, 0.94, 1.01);
  will-change: transform;
}
.list-complete-enter,
.list-complete-leave-active {
  opacity: 0;
}
</style>
