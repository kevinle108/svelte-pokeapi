<script>
  import { goto } from "$app/navigation";
  let searched = ''
  const search = () => {
    goto(`${searched}`)
  }
</script>

<section>
  <div>
    <div>Search a artist</div>
    <input type="text" bind:value={searched}>
    <button on:click={search}>Search</button>
  </div>
</section>