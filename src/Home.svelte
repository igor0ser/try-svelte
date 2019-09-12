<script>
  import { onMount } from 'svelte'
  import axios from 'axios'

  let users = []
  let loading = true

  onMount(async () => {
    const res = await axios.get('https://randomuser.me/api/?results=10')
    console.log(res.data.results);

    users = res.data.results
    loading = false
  })

  const edit = () => {
    console.log('edit');
  }

  const del = () => {
    console.log('del');
  }
</script>

<style>
  .btn {
    margin-right: 16px;
  }
</style>

<div class="row">
  <h1>
    Home page here
  </h1>
  {#if loading}
    <div class="progress">
        <div class="indeterminate"></div>
        </div>
  {:else}
    {#if users.length === 0}
      No users found
    {:else}
      {#each users as user}
        <div class="col s6">
          <div class="card">
            <div class="card-content">
              <p class="card-title">{user.name.first} {user.name.last}</p>
              <p>{user.email}</p>
              <p>{user.phone}</p>
            </div>
            <div class="card-action">
              <button class="btn" on:click={() => edit(user)}>Edit</button>
              <button class="btn" on:click={() => del(user)}>Del</button>
            </div>
          </div>
        </div>
      {/each}
    {/if}
  {/if}
</div>