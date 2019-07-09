<script>
	import TodoList from './TodoList.svelte';
	export let name;

	function resetTodos() {

	}
</script>

<style>
	.body {
		background-color: #efefef;
	}
	.app {
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 18px;
		max-width: 960px;
		margin: 0 auto;
	}
	h1 {
		color: purple;
	}
</style>

<div class="body">
	<div class="app">
		<h1>Todos</h1>
		<TodoList />
	</div>
</div>
