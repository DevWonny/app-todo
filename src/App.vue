<template>
  <Header />
  <Input v-on:add="addTodo" />
  <List v-bind:propsData="todoItems" />
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";
import List from "./components/List.vue";
// import Footer from "./components/Footer.vue";

export default {
  components: {
    Header: Header,
    Input: Input,
    List: List,
  },

  data() {
    return {
      todoItems: [],
    };
  },

  methods: {
    addTodo(add) {
      localStorage.setItem(add, add);
      this.todoItems.push(add);
    },
  },

  created() {
    if (localStorage.length > 0) {
      for (let i = 0; i < localStorage.length; i++) {
        this.todoItems.push(localStorage.key(i));
      }
    }
    console.log(this.todoItems);
  },
};
</script>

<style>
body {
  background-color: #f6f6f8;
}
</style>
