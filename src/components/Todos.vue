<template>
  <h1>Todos</h1>
  <div v-bind:key="todo.id" v-for="todo in todos">
    <Todo
      v-bind:todo="todo"
      @set-completed="$value => { todo.completed = $value }"
      v-on:delete-todo="$emit('delete-todo' , todo.id)"
    />
  </div>
</template>

<script>
import Todo from "./Todo";
export default {
  name: "Todos",
  components: { Todo },
  props: ["todos"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
