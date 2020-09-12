<template>
  <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
    <p>
      <input type="checkbox" @change="isCompleted" />
      {{todo.title}}
      <button @click="$emit('delete-todo' , todo.id)">delete</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    isCompleted() {
      this.$emit("set-completed", !this.todo.completed);
    },
  },
};
</script>

<style scoped>
.todo-item {
  background-color: "white";
}

.is-completed {
  text-decoration: line-through;
}
</style>