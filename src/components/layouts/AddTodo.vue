<template>
	<div>
		<form action="">
			<input type="text" name="todo" placeholder="Add Todo...">
			<input type="submit" value="Submit" class="btn-submit">
		</form>
	</div>
</template>

<script>
	export default {
		name: "AddTodo"
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