<script lang="ts">
    export let handleSliderChange: any;
    export let min: number;
    export let songLoaded: boolean;
    export let duration: number;
    export let sliderValue: number;
</script>

<div class="lg:w-1/2">
    <input
        type="range"
        min={min}
        max={songLoaded ? duration : 0}
        bind:value={sliderValue}
        class="w-full accent-plum"
        on:input={handleSliderChange}
    />
</div>
