<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItemVue
        v-bind:todo="todo"
        v-on:del-todo="$emit('del-todo', todo.id)"
      />
    </div>
  </div>
</template>

<script>
import TodoItemVue from "./TodoItem.vue";
export default {
  name: "Todos",
  components: { TodoItemVue },
  props: ["todos"]
};
</script>

<style scoped></style>
