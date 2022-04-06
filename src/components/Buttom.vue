<template>
  <div class="todo-footer" v-show="todos.length">
    <label for="">
      <input type="checkbox" :checked="doneTodo === todos.length" @change="checkAll"/>
    </label>
    <span> <span>已完成 {{doneTodo}}</span>/ 全部 {{todos.length}}</span>
    <button class="btn btn-danger" @click="clearAll">清除已完成任务</button>
  </div>
</template>


<script>
export default {
  name: "Buttom",
	props:['todos','checkAllTodo','clearAllTodo'],
	computed:{
		doneTodo(){
			return this.todos.reduce((pre,todo)=>pre + (todo.done ? 1:0),0)
		}
	},
	methods:{
		checkAll(e){
			this.checkAllTodo(e.target.checked)
		},
		clearAll(){
			if(confirm("确定全部删除吗？")){
				this.clearAllTodo()
			}
		}
	}
};
</script>


<style scoped>

/*footer*/
.todo-footer {
	height: 40px;
	line-height: 40px;
	padding-left: 6px;
	margin-top: 5px;
}
.todo-footer label{
	display: inline-block;
	margin-right: 20px;
	cursor: pointer;
}
.todo-footer label input{
	position: relative;
	top: -1px;
	vertical-align: middle;
	margin-right: 5px;
}
.todo-footer button{
	float: right;
	margin-top: 5px;
}

</style>