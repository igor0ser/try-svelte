<script>
  import '../node_modules/materialize-css/dist/css/materialize.css'
  import '../node_modules/materialize-css/dist/js/materialize.js'

  import { Router, Route } from 'svelte-routing';
  import Navbar from './Navbar.svelte'
  import Home from './Home/Home.svelte'
  import RandomUsers from './RandomUsers/RandomUsers.svelte'
  import TodoList from './TodoList/TodoList.svelte'

  export let name;
</script>

<style>
</style>

<Router>
  <Navbar />
  <div class="container">
    <Route path="/" component={Home} />
    <Route path="/random-users" component={RandomUsers} />
    <Route path="/todo-list" component={TodoList} />
  </div>
</Router>

