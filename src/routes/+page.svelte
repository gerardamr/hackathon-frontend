<script>
    import { slide } from 'svelte/transition'

	let busName;
    let routes = [56, 201,523,9,901];
    let showItems = false;
    let i = $state(0);

    function searchBus(){
        showItems = true
        for (let x= 0; x < routes.length; x++)
            i++
        return i
    }
</script>


<!-- {#if $currentUser}
    <h1>Seach</h1>
{/if} -->



<div class = "search-wrrapper">
    <label id= "top">Search Bus </label>
    <input type = "search" placeholder = "Enter Bus Number" bind:value={busName}>
    
</div>

<button id = "search" on:click= {searchBus()}>Search</button>

{#if showItems}
	{#each routes.slice(0, i) as item}
		<div id = "routes"transition:slide|global>
			{item}
		</div>
	{/each}
{/if}

<style>
    .search-wrapper{
        margin-inline: auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 3rem;
    }
    #search{
        margin-inline: auto;
        display: flex;
        flex-direction: row;
        align-items: center;
        padding-top: 1;
    }

    #routes{
		padding: 0.5em 0;
		border-top: 1px solid #eee;
        display: flex;

    }
</style>
