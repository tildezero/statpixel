<script context="module">
  export async function load({ page: { params }, fetch }) { 
    const player = params.player
    const req = await fetch(`https://api.slothpixel.me/api/players/${player}`)
    const stats = await req.json()
    if (stats.error) {
      return { 
        status: 404,
        error: "Player not Found"
      }
    }
    return { 
      props: {
        stats
      }
    }
  }
</script>

<script>
  export let stats;
  // import { Accordion, AccordionItem } from 'svelte-collapsible'
</script>
<div class="flex flex-col min-h-screen bg-blue-200">

  <h1 class="mt-4 items-center text-center text-4xl">Stats for {stats.username}</h1>

  <div class="p-3 items-center text-center">
    <h2 class="text-3xl mb-5">Basic</h2>
    <ul>
      <li>UUID: {stats.uuid}</li>
      <li>Rank: {stats.rank}</li>
      <li>Karma: {Number(stats.karma).toLocaleString()}</li>
    </ul>
  </div>

</div>