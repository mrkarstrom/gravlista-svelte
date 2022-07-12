<script>
  import { Router, Route, navigate } from 'svelte-navigator';
  import data from './assets/gravlista.json';
  import Post from './components/Post.svelte';
  import Form from './components/Form.svelte';
  import Nav from './components/Nav.svelte';

  let list = data.data;

  function addPost(namn, senast) {
    const _post = {
      nummer: list.length + 1,
      namn: namn,
      senast: senast,
    };
    list.push(_post);
    list = list;
    navigate('/list');
  }
</script>

<Router>
  <main class="flex flex-col h-screen content-center items-center space-y-4">
    <Nav />
    <Route>
      <Form {addPost} />
    </Route>
    <Route path="list">
      <section class="overflow-auto space-y-4">
        {#each list as listed}
          <Post {...listed} />
        {/each}
      </section>
    </Route>
  </main>
</Router>

<style>
</style>
