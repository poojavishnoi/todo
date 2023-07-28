<template>
  <div id="app">
    <h2>Todo</h2>
    <AddTask />
  </div>
</template>

<script>
import AddTask from "./components/AddTask";
export default {
  name: "App",
  components: {
    AddTask,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.task_input {
  margin: 1rem;
  padding: 0.5rem 1rem;
  border-radius: 1rem;
  border: 1px solid lightgray;
}

button {
  background-color: transparent;
  border-radius: 1rem;
  padding: 0.5rem 1rem;
  border: 1px solid grey;
  font-size: 1rem;
  cursor: pointer;
  margin: 0.5rem;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
}
</style>
