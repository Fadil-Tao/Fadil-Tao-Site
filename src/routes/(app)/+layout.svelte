<script>
	import Navbar from '$lib/components/Navbar.svelte';
    import Player from '$lib/components/player/Player.svelte';
    import '../../app.css'
</script>

<div class="app py-[40px] px-5 md:px-[60px] min-h-screen">
    <video autoplay muted loop id="background-video">
        <source src="./background.webm" type="video/webm">
        Your browser does not support the video tag.
    </video>
    <Player />
    <Navbar />
    <main class="mt-5">
       <slot /> 
    </main>
</div>


<style>
    .app {
        position: relative;
        overflow: hidden;
        min-height: 100vh;
    }

    #background-video {
        position: absolute;
        top: 50%;
        left: 50%;
        width: 100%;
        height: 100%;
        object-fit: cover;
        transform: translate(-50%, -50%);
        z-index: -1;
    }

    .app > *:not(video) {
        position: relative;
        z-index: 1;
    }
</style>
