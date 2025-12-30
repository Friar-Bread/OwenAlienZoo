<script lang="ts">
    import Banner from '$lib/zoo_banner.svelte';
    import sky from '$lib/assets/night_sky.png';
	// instance-level logic goes here
    let fact_num = $state(0);
</script>



<style>
	/* styles go here */
    :global(body), :global(html) {
        margin: 0;
        padding: 0;
        overflow-x: hidden;
    }
    .page {
        position:relative;
        width: 100vw;
        min-height: 1350px;
        margin: 0;
        padding: 0;
        background-color: black;
        background-size: 100% auto;
        background-position: contain;
        background-repeat: repeat-y;

        display: flex;
        align-items: center;
        justify-content: center;
    }
    .content {
        background: rgba(19, 129, 0, 0.6);
        position: absolute;
        top: 125px;
        margin: 0;
        color:white;
        min-height: 300px;
        max-height: 400px;
        padding: 2rem;
        min-width: 1.5vw;
        max-width: 600px;
        width: 85%;
        border-radius: 40px;
    }    
    .facts {
        background: rgba(19, 129, 0, 0.6);
        position:absolute;
        top: 533px;
        margin: 0;
        color:white;
        min-height: 400px;
        padding: 2rem;
        min-width: 1.5vw;
        max-width: 600px;
        width: 85%;
        border-radius: 40px;
    }
    .interact_link {
        background: rgba(19, 129, 0, 0.6);
        text-align: center;
        text-size-adjust: 50;
        position:absolute;
        top: 1050px;
        margin: 0;
        min-height: 150px;
        max-height: 200px;
        padding: 2rem;
        min-width: 1.5vw;
        max-width: 600px;
        width: 85%;
        border-radius: 40px;
    }
    p{
        font-size: 1.75em;
    }
    .interact_text {
        font-size: 4.5em;
        color:white;
    }
</style>


<div 
    class = "page"
    style ="background-image: url('{sky}');"
>
    
    <div class="content">
        <h1>ALIENS</h1>
        <p>No reading the documentation <br>
            lorem ipsum <br>
            blah blah blah <br>
            aliens among us
        </p>
    </div>
    <div class="facts">
        <h1>FACTS - Number {fact_num}</h1>
        <p>No reading the documentation <br>
            lorem ipsum <br>
            blah blah blah <br>
            aliens among us
        </p>
    </div>
    <div class="interact_link">
        <h1 class ="interact_text">Interact with it</h1>
    </div>
    <Banner />
</div>
<button onclick={() => fact_num--}>
	Prev. Fact
</button>
<button onclick={() => fact_num++}>
	Next Fact
</button>