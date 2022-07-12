<script>
  export let namn;
  export let nummer;
  export let senast;
</script>

<div class="card w-96 bg-base-200 shadow-xl">
  <div class="card-body">
    <h2 class="card-title">
      Namn: <span style="text-decoration: underline;">{namn}</span>
    </h2>
    <p class="mb-4">Grav nummer: {nummer}</p>
    <p>Senast begravd: {senast}</p>
    <div class="card-actions justify-end">
      <button class="btn btn-outline ">Mer Info</button>
    </div>
  </div>
</div>
