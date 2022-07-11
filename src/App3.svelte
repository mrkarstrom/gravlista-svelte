<script>
  import data from './assets/gravlista.json';
  import Post from './components/Post.svelte';
  import Form from './components/Form.svelte';

  let list = data.data;

  function addPost(namn, senast) {
    const _post = {
      nummer: list.length + 1,
      namn: namn,
      senast: senast,
    };
    list.push(_post);
    list = list;
  }
</script>

<main class="flex flex-col h-screen content-center items-center space-y-4">
  <Form {addPost} />
  <section class="overflow-auto space-y-4">
    {#each list as listed}
      <Post namn={listed.namn} nummer={listed.nummer} senast={listed.senast} />
    {/each}
  </section>
</main>

<style>
</style>
