<script>
	let busName;
    let routes = [56, 201,523,9,901]
    let showItems = true;
    let i = 5;
    

    function searchBus(busName){
        showItems = true
        return 
    }
    

</script>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
</style>
{#if $currentUser}
    <h1>Seach Bus</h1>
{/if}

{#if showItems}
	{#each routes as item}
		<div>
			{item}
		</div>
	{/each}
{/if}

<div class = 'container'>
    <h1>Search Bus</h1>
</div>
<button on:click= {() => showItems = true} type= "submit">Search</button>
