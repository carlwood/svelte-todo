<script>
    import TodoItem from './TodoItem.svelte';
    let name = 'Todo list';

    let todoItems = [
        { title: 'Wash the car', done: true },
        { title: 'Feed the dog', done: false },
        { title: 'Pick up the kids', done: false },
        { title: 'Beat high score', done: false },
        { title: 'Beat new high score', done: false },
    ]

    let allItems = [];

</script>

<style>
    .todo-list {
        list-style: none;
        margin: 0;
        padding: 0;
        border-top: solid 5px #333;
    }

    .todo-list__item {
        border-bottom: solid 1px #aaa;
    }

    .todo-list__label {
        padding: 1rem;
        width: 100%;
        cursor: pointer;
        display: flex;
        align-items: center;
    }

    @media (min-width: 768px) {
        .todo-list__label {
            padding: 1.5rem;
        }
    }

    .isDone {
        background: lightgreen;
        text-decoration: line-through;
    }

    input {
        margin: 0 1rem 0 0;
    }
</style>

<ul class="todo-list">
    {#each todoItems as item, index }
        <li class="todo-list__item" class:isDone={item.done}>
            <label class="todo-list__label" for="{index}">
                <input id="{index}" value={item.title} type="checkbox" bind:group={allItems} bind:checked={item.done} />
                {item.title}
            </label>
        </li>
    {/each}
</ul>

{#if allItems.length === todoItems.length }
    <p>All items complete!</p>
{/if }