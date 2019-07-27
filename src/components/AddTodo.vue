<template>
  <header class="header">
    <h1>todos</h1>
    <input
      class="new-todo"
      placeholder="What needs to be done?"
      v-model="todo"
      @keyup.enter="addTodo"
    />
  </header>
</template>

<script>
export default {
  data() {
    return {
      todo: ""
    };
  },
  methods: {
    addTodo() {
      this.$store.commit("addTodo", this.todo);
      this.todo = "";
    }
  }
};
</script> 