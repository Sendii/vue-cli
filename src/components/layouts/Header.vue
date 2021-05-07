<template>
	<header class="header">
		<h1>TodoList</h1>
		<div id="nav">
			<router-link to="/">Todo</router-link> |
			<router-link to="/about">About</router-link>
		</div>
	</header>
</template>

<script>
	export default {
		name: "Header"
	}
</script>
<style scoped>
.header{
	background: #333;
	color: #fff;
	text-align: center;
	padding: 10px;
}	
.header a{
	color: #fff;
	padding-right: 5px;
	text-decoration: none;
}
#nav a{
	color: #fff;
}
#nav a.router-link-exact-active{
	color: #fafa;
}
</style>