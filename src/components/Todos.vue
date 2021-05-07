<template>
	<div>
		<div v-for="(todo, index) in p_todos" :key="index">
			<TodoItem :todos="todo" @emDelTodo="$emit('emDelTodo2', todo.id)"/>
		</div>
	</div>
</template>

<script>
	import TodoItem from './TodoItem.vue'
	export default {
		name: "Todos",
		components: {
			TodoItem
		},
		props: ["p_todos"]
	}
</script>

<style>
	
</style>