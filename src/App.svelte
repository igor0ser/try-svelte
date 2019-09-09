<script>
  import '../node_modules/materialize-css/dist/css/materialize.css'
  import '../node_modules/materialize-css/dist/js/materialize.js'

  import { Router, Route } from 'svelte-routing';
  import Navbar from './Navbar.svelte'
  import Home from './Home.svelte'
  import About from './About.svelte'

  export let name;
</script>

<style>
  h1 {
    color: yellow;
    background-color: #333;
    padding: 20px;
  }
</style>

<Router>
  <Navbar />
  <div class="container">
    <Route path="/" component={Home} />
    <Route path="/about" component={About} />
  </div>
</Router>

