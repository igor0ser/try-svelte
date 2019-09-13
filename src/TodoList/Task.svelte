<script>
  import { fly } from 'svelte/transition'

  export let task
  export let completeTask
  export let deleteTask
  let completed


  $: completed = task.completed
  console.log({ completed });
</script>
<style>
  li {
    transition: background-color .5s;
  }
  .completed {
    text-decoration: line-through;
    background: #555
  }
</style>
<li class="collection-item" class:completed transition:fly={{ duration: 300, x: 600 }}>
  <div>
    {task.name}
    <div class="secondary-content">
      <button on:click={() => completeTask(task)}>
        {task.completed ? 'Not done' : 'Done'}
       </button>
       <button on:click={() => deleteTask(task)}>
         Del
        </button>
    </div>
  </div>
</li>
