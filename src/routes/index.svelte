<script context="module">
  import { goto } from '$app/navigation'
  let ign;

  function redir() {
    goto(`/players/${ign}`)
  }
</script>

<div class="flex flex-col justify-center items-center min-h-screen bg-blue-200">

<h1 class="text-3xl pb-5">Statpixel</h1>

<form on:submit|preventDefault={redir} class="p-3"> 
  <input bind:value={ign} placeholder="Enter your IGN" required> 
  <button type="submit" class="border border-black">Go</button>
</form>


<footer>
  <p>
    Created with <a
      class="link"
      target="_blank"
      rel="noopener"
      href="https://svelte.dev">SvelteKit</a
    >
    and deployed with
    <a class="link" target="_blank" rel="noopener" href="https://vercel.com"
      >▲ Vercel</a
    >.
  </p>
</footer>

</div>
