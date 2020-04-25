<template>
  <div class="board">
    <Column
      :key="columnIndex"
      v-for="(taskList, columnIndex) in initialTaskLists"
      :taskList="taskList"
      :columnTitle="columnTitle(columnIndex)"
    />
  </div>
</template>

<script>
import { initialTaskLists } from "../initialTasks";
import { TASK_STATUS_NAME } from "../constants";
import Column from "./Column";

export default {
  components: {
    Column
  },
  data() {
    return {
      initialTaskLists
    };
  },
  methods: {
    columnTitle: function(columnIndex) {
      return TASK_STATUS_NAME[columnIndex];
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
</style>
