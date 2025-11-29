<template>
  <div id="app">
    <!-- <home-com /> -->
    <TodoList />
  </div>
</template>

<script>
// import HomeCom from "./components/Home.vue";
import TodoList from "./components/Todo.vue";
export default {
  name: "App",
  components: { TodoList },
};
</script>

<style></style>
