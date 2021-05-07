<template>
	<div>
		<form @submit.prevent="addTodo">
			<input type="text" v-model="title" name="todo" placeholder="Add Todo...">
			<input type="submit" value="Submit" class="btn-submit">
		</form>
	</div>
</template>

<script>
	import {v4} from 'uuid';
	export default {
		name: "AddTodo",
		data(){
			return{
				title: ''
			}
		},
		methods: {
			addTodo(){
				let newTodo = {
					id: v4(),
					title: this.title,
					completed: false
				}
				this.$emit('em-sendTodo', newTodo)
				this.title = ''
			}
		}
	}
</script>

<style scoped>
form{
	display: flex;
	margin: 5px;
}
input[type="text"]{
	flex: 10;
	padding: 5px;
}
.btn-submit{
	display: inline-block;
	border: none;
	background: #555;
	color: #fff;
	padding: 7px 20px;
	cursor: pointer;
	border-radius: 5px;
}
.btn-submit:hover{
	background: #666;
}
</style>