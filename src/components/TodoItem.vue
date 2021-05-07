<template>
	<div class="todo-item" :class="{'is-complete': todos.completed}">
		<p>
			<input type="checkbox" v-if="todos.completed" checked @change="markComplete">
			<input type="checkbox" v-else @change="markComplete">
			{{todos.title}}
			<button @click="$emit('emDelTodo', todos.id)" class="del">x</button>
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
				this.todoLocal.completed = !this.todoLocal.completed
			}
		}
	}
</script>
<style scoped>
	.todo-item{
		background: #f4f4f4;
		padding: 10px;
		border-bottom: 1px #ccc dotted;
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
</style>