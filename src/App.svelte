<script>
	import TodoList from './TodoList.svelte';
	export let name;

	function resetTodos() {

	}
</script>

<style>
	:global(body) {
		/* this will apply to <body> */
		margin: 0;
		padding: 0;
	}

	:global(*) {
		box-sizing: border-box;
	}

	.app {
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 18px;
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 0.5rem;
	}

	@media (min-width: 768px) {
		.app {
			font-size: 24px;
		}
	}

	h1 {
		color: purple;
		margin-top: 2rem;
	}
</style>

<div class="app">
	<h1>Todos</h1>
	<TodoList />
</div>
