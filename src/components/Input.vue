<template>
  <div class="inputBox">
    <input
      type="text"
      placeholder="Type what you have to do"
      v-model="todoText"
      @keyup.enter="addClick"
    />

    <span class="addContainer" @click="addClick">
      <i class="addBtn fa fa-plus" aria-hidden="true"></i>
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return { todoText: "" };
  },
  methods: {
    addClick() {
      if (this.todoText !== "") {
        let value = this.todoText && this.todoText.trim();
        this.$emit("add", value);
        this.clearInput();
      }
    },
    clearInput() {
      this.todoText = "";
    },
  },
};
</script>

<style scoped>
.inputBox {
  background: #fff;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}

input {
  outline: none;
  width: 84%;
  border: none;
  font-size: 0.9rem;
}
span {
  float: right;
  display: inline-block;
  width: 3rem;
  background: linear-gradient(to right, #6478fb, #8763fb);
  border-radius: 0 5px 5px 0;
  text-align: center;
}
</style>
