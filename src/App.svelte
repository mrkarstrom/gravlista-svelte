<script>
  import data from './assets/gravlista.json';

  let list = data.data;
</script>

<main>
  <h1>Add Post</h1>
  <div class="form-control">
    <label for="post" class="label">Name</label>
    <input type="text" name="author" class="input" placeholder="username" />
    <label for="post" class="label">Post</label>
    <textarea
      name="post"
      id=""
      cols="30"
      rows="10"
      placeholder="Your text here"
    />
  </div>
</main>

<style>
</style>
