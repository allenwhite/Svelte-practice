<script>
    let todos = [
        { done: false, text: 'eat' },
        { done: false, text: 'sleep' },
        { done: false, text: 'code' },
        { done: false, text: 'repeat' }
    ];

    function toggleDone(t) {
        todos = todos.map(todo => {
            if (todo === t) return { done: !t.done, text: t.text };
            return todo;
        })
    }

    let hideDone = false;

    $: filtered = hideDone ? todos.filter(todo => !todo.done) : todos;

    $:showing = filtered.length;

    // for debugging, dear lord

    $:console.log({showing});

</script>

<label>
    <input type="checkbox" bind:checked={hideDone}>
    hide done
</label>

<p>showing {showing} of {todos.length}</p>

<ul>
    {#each filtered as todo}
        <li style="list-style: none;" on:click={() => toggleDone(todo)}>
            {todo.done ? '👍' : ''} {todo.text}
        </li>
    {/each}
</ul>