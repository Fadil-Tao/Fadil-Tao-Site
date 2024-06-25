<script lang="ts">
    export let min:number
    export let maxVolume:number 
    export let volumeSliderValue:number 
    export let changeVolume:any
    import {IconVolume,IconVolumeOff} from '@tabler/icons-svelte'
</script>


<div class="md:flex items-center hidden">
    <div class="flex items-center">
        {#if volumeSliderValue <= 0}
            <IconVolumeOff />
        {:else }
            <IconVolume/>
        {/if}
    </div>
    <input type="range" min={min} bind:value={volumeSliderValue} max={maxVolume}  class="w-full accent-plum" on:input={()=> changeVolume(volumeSliderValue)} />
</div>