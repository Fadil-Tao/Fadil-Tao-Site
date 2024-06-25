<script lang="ts">
    export let img:string
    export let title:string
</script>

<div class=" border-magenta border-2 rounded-xl flex items-center my-2 p-2">
    <div class="lg:w-10 lg:h-10 md:w-6 md:h-6 w-5 h-5">
        <img src={img} alt="" class="contain">
    </div>
    <p class="md:text-base text-xs">{title}</p>
</div>