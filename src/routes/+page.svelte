<script lang="ts">
    import Banner from '$lib/zoo_banner.svelte';
    import sky from '$lib/assets/night_sky.png';
	// instance-level logic goes here
    let fact_num = $state(1);
    $effect(() =>  {
        if (fact_num===4) {fact_num = 1;}
        else if (fact_num===0) {fact_num = 3;}
    });
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
        position: relative;
        bottom:-25px;
        min-width: 300px;
        font-size: 4.5em;
        color:white;
    }
    .good-button{
        font-size:2em;
        position:absolute;
        padding: 10px;
        top: auto;
        cursor: pointer;
        border-radius: 15px;
        border: none;
        background-color: rgba(223, 253, 233, 0.9);
    }
    .good-button:hover{
        background-color: rgba(161, 183, 168, 0.75);
    }
    .decrease_but{
        left: 300px;
    }
    .increase_but{
        right: 300px;
    }
    
</style>


<div 
    class = "page"
    style ="background-image: url('{sky}');"
>
    
    <div class="content">
        <h1>ALIENS</h1>
        <p>This page will tell you about aliens <br>
            The mysterious beings from outer space <br>
            Little green men <br>
            Knowing the facts could save your life.
        </p>
    </div>
    <div class="facts">
        <h1>FACTS - Number {fact_num}</h1>
        {#if fact_num === 1}
            <p>Aliens are very real <br>
                They are all around us <br>
                Be nice to aliens <br>
                aliens are among us
            </p>
        {:else if fact_num === 2}
            <p>Aliens can not eat burgers and other meats <br>
                This is because they are vegetarian. <br>
                It is still unsure if they will eat beyond burgers <br>
                Human flesh eating aliens are super unlikely
            </p>
        {:else if fact_num === 3}
            <p>Aliens do not like water <br>
                Don't take them to the swimming pool with you <br>
                This is because their home planet is very dry. <br>
                They can swim in bromine if you have it.
            </p>
        {/if}
        
    </div>
    <button onclick={() => fact_num--} class="decrease_but good-button">
        Prev. Fact
    </button>
    <button onclick={() => fact_num++} class="increase_but good-button">
        Next Fact
    </button>
    <div class="interact_link">
        <a href="/interact" class ="interact_text">Interact with it</a>
    </div>
    <Banner />
</div>