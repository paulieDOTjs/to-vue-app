<template>
  <div id="app">
    <Header />
    <AddToDo v-on:add-toDo="AddToDo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/Layout/Header";
import AddToDo from "./components/AddToDo";

export default {
  name: "App",
  components: { Todos, Header, AddToDo },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "To do 1",
          completed: false
        },
        {
          id: 2,
          title: "To do 2",
          completed: false
        },
        {
          id: 3,
          title: "To do 3",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    AddToDo(newToDo) {
      this.todos = [...this.todos, newToDo];
    }
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

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>
