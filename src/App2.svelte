<script>
  import data from './assets/gravlista.json';

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
      <div class="card w-96 bg-base-200 shadow-xl">
        <div class="card-body">
          <h2 class="card-title">
            Namn: <span style="text-decoration: underline;">{listed.namn}</span>
          </h2>
          <p class="mb-4">Grav nummer: {listed.nummer}</p>
          <p>Senast begravd: {listed.senast}</p>

          <div class="card-actions justify-end">
            <button class="btn btn-outline ">Mer Info</button>
          </div>
        </div>
      </div>
    {/each}
  </section>
</main>

<style>
</style>
