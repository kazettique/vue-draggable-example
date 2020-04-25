<template>
  <div class="column">
    <h3 class="column-title">{{ columnTitle }}</h3>
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    columnTitle: String
  }
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
</style>
