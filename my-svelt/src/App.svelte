<script>
  import Todo from './Todo.svelte';
  let title = ''
  let todos = []
  let id = 0

  function createTodo() {
    todos.push({
      id,
      title,
    });
    todos = todos

    title = ''
    id += 1
  }
</script>

<input type="text" bind:value={title}/>
<button type="button" on:click={createTodo}>
  Create To Do
</button>

{#each todos as todo}
  <Todo {todo} />
{/each}
