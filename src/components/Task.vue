<template>
  <div class="task">
    <strong>[IT-{{ task.id }}]</strong>
    <h4>{{ task.content }}</h4>
  </div>
</template>

<script>
export default {
  props: {
    task: Object
  }
};
</script>

<style lang="scss" scoped>
.task {
  margin: 10px;
  height: 50px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  cursor: grab;
  background: #ffffff;
  padding: 10px;
  transition: transform 0.25s cubic-bezier(0.02, 1.01, 0.94, 1.01);
  will-change: transform;
}
</style>
