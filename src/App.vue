<template>
  <div id="app"></div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      todos: [
        {
          id: 1,
          todo: "To do 1",
          completed: false
        },
        {
          id: 2,
          todo: "To do 2",
          completed: false
        },
        {
          id: 3,
          todo: "To do 3",
          completed: false
        }
      ]
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
