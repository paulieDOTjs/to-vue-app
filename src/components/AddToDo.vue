<template>
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title" placeholder="Add to do" />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";

export default {
  name: "AddToDo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addToDo(e) {
      e.preventDefault();
      const newToDo = {
        id: uuidv4(),
        title: this.title,
        completed: false
      };
      this.$emit("add-toDo", newToDo);
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
</style>
