<script>
  import Navbar from './Navbar.svelte'
  import Player from './Player.svelte'
  import AddPlayer from './AddPlayer.svelte'

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
  
  const addPlayer = (e) => {
    const { player } = e.detail;
    players = [...players, player];
  }

  const removePlayer = (e) => {
    players = players.filter( player => player.name !== e.detail)
  }
</script>

<Navbar />
<main class="container">
  
  <AddPlayer on:addplayer={addPlayer} />
  
  {#if players.length === 0}
    <h1>No players</h1>
    <p>Add some one on the form above</p>
  {:else}
    {#each players as player}
      <Player name={player.name} points={player.points} on:removeplayer={removePlayer}/>
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