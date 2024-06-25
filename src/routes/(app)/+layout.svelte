<script>
	import Navbar from '$lib/components/Navbar.svelte';
    import Player from '$lib/components/player/Player.svelte';
    import '../../app.css'
</script>

<div class="app py-[40px] px-5 md:px-[60px] min-h-screen">
    <Player />
    <Navbar />
    <main class="mt-5">
       <slot /> 
    </main>
</div>


<style>
    .app{
        background: url("./background.gif");
        background-size: cover  ;
        background-repeat: no-repeat    ;
    }
</style>