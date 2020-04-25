<template>
  <div class="board">
    <Column
      :key="columnIndex"
      v-for="(taskList, columnIndex) in initialTaskLists"
      :columnTitle="columnTitle(columnIndex)"
    >
      <Draggable class="draggable" :list="taskList" group="columnGroup">
        <Task :key="task.id" v-for="task in taskList" :task="task" />
      </Draggable>
    </Column>
  </div>
</template>

<script>
import { initialTaskLists } from "../initialTasks";
import { TASK_STATUS_NAME, GROUP_TYPE } from "../constants";
import Column from "./Column";
import Task from "./Task";
import Draggable from "vuedraggable";

export default {
  components: {
    Column,
    Task,
    Draggable
  },
  data() {
    return {
      initialTaskLists
    };
  },
  methods: {
    columnTitle: function(columnIndex) {
      return TASK_STATUS_NAME[columnIndex];
    },
    columnGroup: function() {
      return GROUP_TYPE.TASK;
    }
  }
};
</script>

<style lang="scss" scoped>
.board {
  margin: 50px;
  display: flex;
  width: auto;
  background: #ffffff;
  border: 1px dashed #000000;
  justify-content: center;
}

.draggable {
  // background: lightpink;
  min-height: 100%;
  // border-top: 1px solid black;
}

.transition-group {
  background: lightgreen;
  display: inline-block;
  min-height: 30px;
}
</style>
