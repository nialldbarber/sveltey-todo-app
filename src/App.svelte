<script>
  import Todos from "./components/Todos.svelte";
  import Form from "./components/Form.svelte";

  let todos = [
    { id: 1, todo: "learn svelte" },
    { id: 2, todo: "learn react" },
    { id: 3, todo: "learn vue" }
  ];
  let todo = "";

  const handleSubmit = e => {
    e.preventDefault();
    todos = [...todos, { id: Math.random(), todo: todo }];
    todo = "";
  };
</script>

<style>
  .todo-container {
    padding: 1rem;
  }
</style>

<div class="todo-container">
  <h1>Todos</h1>
  <form on:submit={handleSubmit}>
    <label>
      <input type="text" bind:value={todo} />
    </label>
  </form>
  <Todos {todos} />
</div>
