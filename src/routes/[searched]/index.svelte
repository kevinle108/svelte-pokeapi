<script>
  import { page } from "$app/stores";
  import { onMount } from "svelte";

  const searched = $page.params.searched
  let pokeImageUrl = 'https://upload.wikimedia.org/wikipedia/commons/thumb/5/53/Pok%C3%A9_Ball_icon.svg/1200px-Pok%C3%A9_Ball_icon.svg.png'

  onMount(async () => {
    const pokesearch = await fetch(`https://pokeapi.co/api/v2/pokemon/${searched}`)
    const res = await pokesearch.json()
    const id = res.id
    const url = `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/${id}.png`
    pokeImageUrl = url
    console.log(res)
  });
</script>

<h1>You searched: {searched}</h1>
<img id="pokemon-image" src={pokeImageUrl} alt="">

<style>
  #pokemon-image {
    max-width: 400px;
    margin: 0 auto;
    display: block;
  }
</style>