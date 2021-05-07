<template>
	<div class="todo-item" :class="{'is-complete': todos.completed}">
		<p>
			<input type="checkbox" v-if="todos.completed" checked @change="markComplete">
			<input type="checkbox" v-else @change="markComplete">
			{{todos.title}}
			<button @click="$emit('emDelTodo', todos.id)" v-if="todos.completed" class="del">x</button>
		</p>
	</div>
</template>

<script>
	export default{
		name: "TodoItem",
		props: ["todos"],
		data(){
			return {
				todoLocal: this.todos
			}
		},
		methods: {
			markComplete(){
				this.todoLocal.completed = (this.todoLocal.completed ? false : true)
			}
		}
	}
</script>
<style scoped>
	.todo-item{
		background: #f4f4f4;
		padding: 10px;
		border-bottom: 1px #ccc dotted;
		margin: 5px;
		border-radius: 5px;
	}
	.todo-item:hover{
		background: #d1d1d1;
	}
	.is-complete{
		text-decoration: line-through;
	}
	.del{
		background: #ff0000;
		color: #fff;
		border: none;
		padding: 5px 9px;
		border-radius: 50%;
		cursor: pointer;
		float: right;
	}
	.del:hover{
		background: #f76363;
		color: #000;
	}
	input[type="checkbox"]{
		cursor: pointer;
	}
</style>