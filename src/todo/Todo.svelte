<script>
  import TodoList from "./TodoList.svelte";

  let data = [
    {
      id: Date.now(),
      name: "test1",
      description: "test desc1",
      completed: true,
    },
  ];
  let taskName = "";
  let taskDescription = "";

  const handleAddTodo = () => {
    data = [
      ...data,
      {
        id: Date.now(),
        name: taskName,
        description: taskDescription,
        completed: false,
      },
    ];

    taskName = "";
    taskDescription = "";
  };

  const handleDelete = (value) => {
    data = data.filter((item) => item.id !== value.detail.id);
  };

  const markComplete = (value) => {
    data = data.map((item) => {
      if (item.id === value.detail.id) {
        item.completed = !item.completed;
      }
      return item;
    });
  };
</script>

<div>
  <input placeholder="task name" bind:value={taskName} />
  <input placeholder="description name" bind:value={taskDescription} />
  <button on:click|preventDefault={handleAddTodo}>Add</button>
</div>
{#each data as item}
  <TodoList {item} on:delete={handleDelete} on:markComplete={markComplete} />
{/each}
