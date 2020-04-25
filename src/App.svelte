<script>
  import Navbar from './Navbar.svelte'
	let name = "Lincoln";
  let points = 100;
  let showControls = false;
  
  const addPoint = () => points +=1;
  const removePoint = () => points -=1;
  const toggleControls= () => showControls = !showControls;
</script>

<Navbar />
<main class="container">
  <div class="card">
    <h1>
      {name}
      <button class="btn btn-sm" on:click={toggleControls}>
        {#if showControls }-{:else}+{/if}
      </button>
    </h1>
    <h3>Points: {points}</h3>
    {#if showControls }
      <button class="btn" on:click={addPoint}>+1</button>
      <button class="btn btn-dark" on:click={removePoint}>-1</button>
      <input type="number" name="" id="" bind:value={points}>
    {/if}
  </div>
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

  .btn {
    box-sizing: border-box;
    padding: 0 5px;
    min-width: 22px;
    outline: none;
  }
  .btn-sm {
    font-size: 0.5em;
  }

  .card{
    border: 1px solid #ccc;
    border-radius: 5px;
  }

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>