<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";

  const searched = $page.params.searched

  onMount(async () => {
    const itunesSearched = await fetch(`https://itunes.apple.com/search?term=${searched}&entity=song`);
    const res = await itunesSearched.json();
    console.log(res)
  });
  // https://itunes.apple.com/search?term=nas&entity=song
</script>

<h1>You searched: {searched}</h1>
<section>
  <div></div>
</section>

<style>

</style>