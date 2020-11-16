<template>
  <div id="app">
    <h1>To-Do List</h1>
    <to-do-form />
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <to-do-item
          :label="item.label"
          :done="item.done"
          :id="item.id"
        ></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script>
import ToDoItem from "./components/ToDoItem";
import ToDoForm from "./components/ToDoForm";

export default {
  name: "App",
  components: {
    ToDoItem,
    ToDoForm,
  },
  data() {
    return {
      ToDoItems: [
        { label: "Learn Vue", done: false },
        { label: "Create a Vue project with the CLI", done: true },
        { label: "Have fun", done: true },
        { label: "Create a to-do list", done: false },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  list-style-type: none;
}
</style>
