<script>
  import data from './assets/gravlista-short.json';

  let list = data.data;
</script>

<main class="flex flex-col h-screen content-center items-center space-y-4">
  <h1 class="text-5xl font-bold py-6">Gravlista</h1>
  <div class="form-control">
    <div class="input-group">
      <input type="text" placeholder="Search…" class="input input-bordered" />
      <button class="btn btn-square">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          ><path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
          /></svg
        >
      </button>
    </div>
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
