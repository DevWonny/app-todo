<template>
  <Header></Header>
  <Input></Input>
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";
// import List from "./components/List.vue";
// import Footer from "./components/Footer.vue";

export default {
  components: {
    Header: Header,
    Input: Input,
  },
};
</script>

<style>
body {
  background-color: #f6f6f8;
}
</style>
