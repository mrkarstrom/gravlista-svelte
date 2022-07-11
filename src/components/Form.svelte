<script>
  export let addPost;
  let namn = '';
  let senast = '';
  let nummer = '';

  function sendAddPost() {
    addPost(namn, nummer);
    namn = '';
    nummer = '';
  }
</script>

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
  <button
    on:click={() => {
      sendAddPost;
    }}
    class="btn btn-outline my-3">Skicka</button
  >
</div>
