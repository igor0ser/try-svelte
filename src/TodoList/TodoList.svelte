<script>
  import FormModal from './FormModal.svelte'
  import Task from './Task.svelte'

  let tasks = [{ name: '123', completed: true }]

  const addItem = (taskName) => {
    tasks = [...tasks, { name: taskName, completed: false }]
  }

  const completeTask = (task) => {
    tasks = tasks.map(t => t === task ? { ...task, completed: !task.completed } : t)
  }

  const deleteTask = (task) => {
    tasks = tasks.filter(t => t !== task)
  }
</script>

<div>
  <h1>
    Todo List
  </h1>
  <FormModal {addItem} />

  <ul class="collection">
    {#each tasks as task}
      <Task {task} {completeTask} {deleteTask} key={task.name} />
    {/each}
  </ul>
</div>