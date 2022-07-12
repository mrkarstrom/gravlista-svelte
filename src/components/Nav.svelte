<script>
  import { Link, useLocation } from 'svelte-navigator';
  const location = useLocation();
</script>

<div class="flex space-x-4">
  <Link to="/" class={$location.pathname === '/' ? 'underline' : ''}
    >Add Post</Link
  >
  <Link to="/list" class={$location.pathname === '/list' ? 'underline' : ''}
    >Posts</Link
  >
</div>
