<script>
    import TodoItem from './TodoItem.svelte';
    let name = 'Todo list';
    let todoItems = [];

    let nextId = todoItems.length + 1;

    // let nextId = 2;
    let allItems = [];
    let newTodoTitle = '';

    function addTodo(e) {
        if (e.key === 'Enter' && e.target.value) {
            todoItems = [{
                id: nextId,
                title: e.target.value,
                done: false
            }, ...todoItems]

            nextId = nextId + 1
            newTodoTitle = ''
        }
    }

    function handleDeleteTodo(event) {
        todoItems = todoItems.filter(todoItem => todoItem.id !== event.detail.id);
    }

    function deleteAllTodos() {
        todoItems = []
    }

</script>

<style>
    .todo-list {
        list-style: none;
        margin: 0;
        padding: 0;
        border-top: solid 5px #333;
    }
    input {
        border: solid 5px #ddd;
        width: 100%;
    }
</style>

<input type="text" placeholder="Add todo" bind:value={newTodoTitle} on:keydown={addTodo}/>
<ul class="todo-list">
    {#each todoItems as item, index }
        <TodoItem {...item} on:deleteTodo={handleDeleteTodo} />
    {/each}
</ul>
<br>

{#if todoItems.length}
    <button on:click={deleteAllTodos}>Delete all</button>
{/if}

{#if !todoItems.length}
    <p>No todos - add one!</p>
{/if}
