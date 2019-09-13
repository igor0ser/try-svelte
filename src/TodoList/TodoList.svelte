<script>
  import FormModal from './FormModal.svelte'

  let items = []

  const addItem = (newItem) => {
    items = [...items, newItem]
  }
</script>

<div>
  <h1>
    Todo List
  </h1>
  <FormModal {addItem} />
  <hr />
  {items.toString()}
</div>