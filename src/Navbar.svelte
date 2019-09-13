<script>
  import { Link } from 'svelte-routing';
</script>

<nav>
  <div class="nav-wrapper container">
    <Link to="/">
      <span class="brand-logo">Svelte</span>
    </Link>
    <ul id="nav-mobile" class="right hide-on-med-and-down">
      <li><Link to="/">Home</Link></li>
      <li><Link to="/random-users">Random users</Link></li>
      <li><Link to="/todo-list">Todo list</Link></li>
    </ul>
  </div>
</nav>