<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let item = {};

  const deleteItem = () => {
    dispatch("delete", { id: item.id });
  };
  const markComplete = () => {
    dispatch("markComplete", { id: item.id });
  };
</script>

<div>
  <div class="listItemContainer">
    <div class:checked={item.completed}>{item.id}</div>
    <div class:checked={item.completed}>{item.name}</div>
    <div class:checked={item.completed}>{item.description}</div>
    <div>
      <button on:click={deleteItem}>Delete</button>
      <button on:click={markComplete}>Complete</button>
    </div>
  </div>
</div>

<style>
  .listItemContainer {
    display: flex;
    border: 1px solid lightgray;
  }
  .listItemContainer > div {
    padding: 1rem;
  }

  .checked {
    text-decoration: line-through;
  }
</style>
