<script>
  import { onMount } from 'svelte'
  export let addItem

  let modalEl
  let modalInstance
  let taskName
  
  onMount(() => {
    modalInstance = M.Modal.init(modalEl)
  })

  const submit = () => {
    addItem(taskName)
    taskName = ''
  }
</script>

<div>

  <button data-target="modal1" class="btn modal-trigger">Modal</button>

  <!-- Modal Structure -->
  <div id="modal1" class="modal" bind:this={modalEl}>
    <form on:submit|preventDefault={submit}>
      <div class="modal-content">
        <label for="task-name">Task name</label>
        <input id="task-name" bind:value={taskName} />
      </div>
      <div class="modal-footer">
        <button class="modal-close btn-flat">Create</button>
      </div>
    </form>
  </div>

</div>