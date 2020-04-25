<script>
  import Navbar from './Navbar.svelte'
  import Player from './Player.svelte'

  let players = [
    {
      name: "Benjamin",
      points: 54
    },
    {
      name: "Vicente",
      points: 60
    },
    {
      name: "Luciana",
      points: 70
    }
  ];

</script>

<Navbar />
<main class="container">
  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as player}
      <Player name={player.name} points={player.points} />
    {/each}
  {/if}
  
  
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 500px;
		margin: 0 auto;
	}

  h1 {
    color: #ff3e00;
    font-weight: 100;
  }

</style>