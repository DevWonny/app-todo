<template>
  <ul>
    <li v-for="item in propsData">{{ item }}</li>
  </ul>
</template>

<script>
export default {
  props: ["propsData"],
};
</script>

<style></style>
