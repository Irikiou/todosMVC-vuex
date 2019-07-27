<template>
  <footer class="footer" v-show="$store.state.todoList.length">
    <!-- This should be `0 items left` by default -->
    <span class="todo-count">
      <strong>{{$store.getters.leftCount}}</strong> item left
    </span>
    <!-- Remove this if you don't implement routing -->
    <ul class="filters">
      <li>
        <router-link to="/" active-class="selected" exact>All</router-link>
        <!-- <a class="selected" href="#/">All</a> -->
      </li>
      <li>
        <router-link to="/active" active-class="selected">Active</router-link>
        <!-- <a href="#/active">Active</a> -->
      </li>
      <li>
        <router-link to="/completed" active-class="selected">Completed</router-link>

        <!-- <a href="#/completed">Completed</a> -->
      </li>
    </ul>
    <!-- Hidden if no completed items are left ↓ -->
    <button
      class="clear-completed"
      @click="clrCmp"
      v-show="$store.getters.leftCount != $store.state.todoList.length"
    >Clear completed</button>
  </footer>
</template>

<script>
export default {
  methods: {
    clrCmp() {
      this.$store.commit("clrCmp");
    }
  }
};
</script>