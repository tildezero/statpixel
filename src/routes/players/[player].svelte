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
</script>

<p>{stats.username}'s UUID is {stats.uuid}</p>
