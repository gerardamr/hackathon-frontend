<script>
    let busName= $state(["1","2","3","4"]);
    let routes = $state([]);
    let listlen = $state(routes.length);
    let i = 0;
    let showItems = $state(false);

    function Bus(id, name, coordinate, routes) {
        this.id = id;
        this.Name = name;
        this.coord = coordinate;
        this.routes = routes;
    }

    function addBus(Bus){
        busName.push(Bus)
    }

</script>



<div class = "search-wrapper">
    <label for='search'>Search Bus</label>
    <input type ="search" id ="search"/>
    <button on:click={() => showItems = true}>Search</button>
</div>



{#if showItems}
	{#each busName.slice(0, listlen) as item}
		<div id= 'searchResult'>
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
        padding-top: 100px;
    }
    #searchResults{
        bottom: 0
    }
</style>;