<template>
  <ul class="todo-main">
    <Item v-for="todoObj in todos" :key="todoObj.id" :todo="todoObj"></Item>
  </ul>
</template>


<script>
import Item from "./Item.vue";

export default {
  name: "List",
  components: {
    Item,
  },
  data() {
    return {
      todos: [
        { id: "0001", title: "吃饭", done: true },
        { id: "0002", title: "喝酒", done: true },
        { id: "0003", title: "睡觉", done: true },
      ],
    };
  },
};
</script>


<style scoped>
/*main*/
.to-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}
.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>