<template>
  <div class="app">
    <h1>{{ title }}</h1>
    <Counter />
    <TodoList />
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";
import TodoList from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    Counter,
    TodoList,
  },
  data() {
    return {
      title: "Vue 示例项目",
    };
  },
};
</script>

<style>
.app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
