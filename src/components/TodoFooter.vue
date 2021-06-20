<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" @click="clearTodo">전체 지우기</span>
  </div>
</template>

<script>
export default {
  methods: {
    clearTodo() {
      this.$emit('removeAll');
    }
  }
}
</script>

<style scoped>
  .clearAllContainer {
    width:8.5rem;
    height: 50px;
    line-height: 50px;
    background-color: rgb(253, 232, 245);
    border-radius: 5px;
    margin: 0 auto;
  }
  .clearAllBtn {
    color: #e20303;
    display: black;
    font-family: 'Poor Story', cursive;
  }
</style>