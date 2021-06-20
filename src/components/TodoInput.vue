<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" placeholder="여기에 할 일을 입력해보세요"
    v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
      <i class="addBtn fas fa-plus" aria-hidden="true"></i>
    </span>
    </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ''
    }
  },
  methods: {
    addTodo() {
        if(this.newTodoItem !== "") {
        var value = this.newTodoItem && this.newTodoItem.trim();
        this.$emit('addTodo', value);
        this.clearInput();
      }
    },
    clearInput() {
      this.newTodoItem = '';
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poor+Story&display=swap');
  input:focus {
    outline: none;
  }
  .inputBox {
    background: white;
    height: 50px;
    line-height: 50px;
    border-radius: 5px;
    }
  .inputBox input {
    border-style: none;
    font-size: 1rem;
    font-family: 'Poor Story', cursive;
  }
  .addContainer {
    float: right;
    background: linear-gradient(to right, #ee64fb, #f89ef4);
    display: block;
    width: 3rem;
    border-radius: 0 5px 5px 0;
  }
  .addBtn {
    color: white;
    vertical-align: middle;
  }

</style>