<template>
  <div>
    <form @submit="addTodo">
      <input
        tybe="text"
        v-model="title"
        name="title"
        placeholder="Add Todo..."
      />
      <button tybe="submit">Add Todo</button>
    </form>
  </div>
</template>

<script>
import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuid,
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>
