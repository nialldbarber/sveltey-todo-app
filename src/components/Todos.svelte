<script>
  export let todos;
</script>

<ul>
  {#each todos as { id, todo }}
    <li>{todo}</li>
  {/each}
</ul>
