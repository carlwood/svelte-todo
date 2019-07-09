<script>
    import TodoItem from './TodoItem.svelte';
    let name = 'Todo list';

    let todoItems = [
        { title: 'Wash the car', done: true },
        { title: 'Feed the dog', done: false }
    ]
</script>

<style>
    .is-done {
        background: lightgreen;
    }

    label {
        padding: 1rem;
        width: 100%;
        cursor: pointer;
    }

    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>

<ul>
    
    {#each todoItems as item, index }
        <li class="{item.done ? 'is-done' : ''}">
            <label for="{index}">
                {item.title}
                <input id="{index}" type="checkbox" bind:checked={item.done} />
            </label>
        </li>
    {/each}
</ul>