<script lang="ts">
    export let isPlaying:boolean;
    export let startSong:MouseEventHandler<HTMLButtonElement>;
    export let nextSong:any
    export let prevSong:any

    import {IconPlayerPause,IconPlayerPlayFilled, IconPlayerSkipBackFilled, IconPlayerSkipForwardFilled} from '@tabler/icons-svelte';
	import type { MouseEventHandler } from 'svelte/elements';
</script>


<div class="flex md:mx-5 lg:mx-10 items-center">
    <button on:click={prevSong}>
        <IconPlayerSkipBackFilled />
    </button>
    <button class="mx-3" on:click={startSong}>
        {#if !isPlaying}
            <IconPlayerPlayFilled />
        {:else}
            <IconPlayerPause />
        {/if}
    </button>
    <button on:click={nextSong}>
        <IconPlayerSkipForwardFilled />
    </button>
</div>