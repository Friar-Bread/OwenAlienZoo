<!-- Second page with alien interaction -->
<script lang="ts">
    import Banner from '$lib/zoo_banner.svelte';
    import sky from '$lib/assets/night_sky.png';
    import lil_alien from '$lib/assets/lil_alien.png'
    import lil_alien_annoy from '$lib/assets/lil_alien_annoyed.png'
	// instance-level logic goes here
    let currentImage = $state(lil_alien);
    let timeoutId: number | undefined;

    function toggleImage() {
    currentImage =  lil_alien_annoy;
    clearTimeout(timeoutId);

    timeoutId = setTimeout(() => {
        currentImage = lil_alien;
    }, Math.random() * (10000 - 2000) + 2000);
    }
    
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
        min-height: 100vh;
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
        min-height: 550px;
        max-height: 550px;
        padding: 2rem;
        min-width: 1.5vw;
        max-width: 450px;
        width: 85%;
        border-radius: 40px;
    }     

</style>
<div 
    class = "page"
    style ="background-image: url('{sky}');">
    <Banner />
    <div class="content">
        <h1>Interact with an alien.</h1>
        <button onclick={toggleImage}>
            <img src = "{currentImage}" alt= "an alien" height="430px" >
        </button>
        <a href="/" color = pink><br><mark>Go back home</mark></a>
    </div>
    
</div>

