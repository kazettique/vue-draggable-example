<template>
  <div class="column">
    <h3 class="column-title">{{ columnTitle }}</h3>
    <Draggable class="draggable" v-model="cList" :group="groupName()">
      <transition-group name="list-complete">
        <Task :key="task.id" v-for="task in cList" :task="task" />
      </transition-group>
    </Draggable>
  </div>
</template>

<script>
import Task from "./Task";
import Draggable from "vuedraggable";
import { GROUP_TYPE } from "../constants";

export default {
  components: { Task, Draggable },
  props: {
    taskList: Array,
    columnTitle: String
  },
  data() {
    return {
      cList: this.taskList
    };
  },
  methods: {
    groupName: function() {
      return GROUP_TYPE.TASK;
    }
  }
  // watch: {
  //   cList: function(newList, oldList) {
  //     console.log(newList);
  //     console.log(oldList);
  //   }
  // }
};
</script>

<style lang="scss" scoped>
.column {
  margin: 10px;
  background: #ffffff;
  width: 300px;
  background: rgb(233, 240, 249);
  padding-top: 10px;
  padding-bottom: 100px;
}

.column-title {
  text-align: center;
  text-transform: uppercase;
}

.draggable {
  background: lightpink;
  min-height: 50px;
}
</style>
