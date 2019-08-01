<script>
    import { createEventDispatcher } from 'svelte';

    let name = 'Todo list';
    export let title;
    export let index;
    export let done;
    export let id;

    const dispatch = createEventDispatcher();

    function deleteTodo() {
        dispatch('deleteTodo', {
            id: id
        })
    }
</script>

<style>
    .todo-list__label {
        padding: 1rem;
        width: 100%;
        cursor: pointer;
        display: flex;
        align-items: center;
    }

    .todo-list__item {
        border-bottom: solid 1px #aaa;
        position: relative;
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

    button {
        position: absolute;
        right: 1rem;
        top: 50%;
        transform: translateY(-50%);
        width: 30px;
        height: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        /* color: purple; */
        border: solid 2px purple;
        line-height: 1;
        /* color: #fff; */
        border-radius: 100%;
        font-size: 1rem;
    }
</style>

<li class="todo-list__item" class:isDone={done}>
    <label class="todo-list__label" for="{index}">
        <input id="{index}" value={title} type="checkbox" bind:checked={done} />
        {title}
    </label>
    <button on:click={deleteTodo}>&times;</button>
</li>
