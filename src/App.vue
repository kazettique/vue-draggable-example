<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <!-- <DraggableExample /> -->
    <!-- <DraggableExample2 /> -->
    <h1>JIRA Board made with VueDraggable</h1>
    <Board />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
// import DraggableExample from "./components/DraggableExample";
// import DraggableExample2 from "./components/DraggableExample2";
import Board from "./components/Board";

export default {
  name: "App",
  components: {
    // HelloWorld,
    // DraggableExample,
    // DraggableExample2,
    Board
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px auto;
}
</style>
