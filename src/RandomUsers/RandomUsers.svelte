<script>
  import axios from 'axios/index'
</script>

<style>
  .btn {
    margin-right: 16px;
  }
</style>

<div class="row">
  <h1>Random users</h1>
  {#await axios.get('https://randomuser.me/api/?results=10')}
    <div class="progress">
      <div class="indeterminate"></div>
    </div>
  {:then res }
    {#if res.data.results.length === 0}
      No users found
    {:else}
      {#each res.data.results as user}
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
  {:catch error}
    <div class="card blue-grey darken-1">
      <div class="card-content white-text">
        <span class="card-title">Fetch failed</span>
      </div>
    </div>
  {/await}
</div>