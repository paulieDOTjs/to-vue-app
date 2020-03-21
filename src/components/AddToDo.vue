<template>
  <div>
    <form @submit="addToDo">
      <input type="text" v-model="title" name="title" placeholder="Add to do" />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
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
        title: this.title,
        completed: false
      };
      this.$emit("add-toDo", newToDo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
</style>
