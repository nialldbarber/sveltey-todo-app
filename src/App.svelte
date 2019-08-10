<script>
  import Todo from "./Todo.svelte";

  let todos = [
    { id: 1, todo: "learn svelte" },
    { id: 2, todo: "learn react" },
    { id: 3, todo: "learn vue" }
  ];
  let todo = "";

  const handleSubmit = e => {
    e.preventDefault();
    console.log(todo);
    todos = [...todos, { id: Math.random(), todo: todo }];
  };
</script>

<style lang="scss">
  .todo-container {
  }
</style>

<div class="todo-container">
  <h1>Todos</h1>
  <form on:submit={handleSubmit}>
    <label>
      <input type="text" bind:value={todo} />
    </label>
  </form>
  <ul>
    {#each todos as { id, todo }}
      <li>{todo}</li>
    {/each}
  </ul>
</div>
