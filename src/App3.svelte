<script>
  import data from './assets/gravlista.json';
  import Post from './components/Post.svelte';

  let namn = '';
  let senast = '';
  let nummer = '';

  let list = data.data;

  function addPost() {
    const _post = {
      nummer: list.length + 1,
      namn: namn,
      senast: senast,
    };
    list.push(_post);
    list = list;
    namn = '';
    senast = '';
  }
</script>

<main class="flex flex-col h-screen content-center items-center space-y-4">
  <h1 class="text-5xl font-bold py-6">Gravlista</h1>

  <div class="form-control w-full max-w-xs">
    <label class="label" for="namn">
      <span class="label-text">Lägg till</span>
    </label>
    <input
      bind:value={namn}
      type="text"
      name="namn"
      placeholder="Namn"
      class="input input-bordered w-full max-w-xs"
    />
    <!-- <label class="label" for="nummer">
      <span class="label-text">Nummer</span>
    </label>
    <input
      bind:value={nummer}
      type="text"
      name="nummer"
      placeholder="Nummer"
      class="input input-bordered w-full max-w-xs"
    /> -->
    <label class="label" for="senast">
      <span class="label-text">Senast</span>
    </label>
    <input
      bind:value={senast}
      type="text"
      name="senast"
      placeholder="År"
      class="input input-bordered w-full max-w-xs"
    />
    <button on:click={addPost} class="btn btn-outline my-3">Skicka</button>
  </div>

  <section class="overflow-auto space-y-4">
    {#each list as listed}
      <Post namn={listed.namn} nummer={listed.nummer} senast={listed.senast} />
    {/each}
  </section>
</main>

<style>
</style>
