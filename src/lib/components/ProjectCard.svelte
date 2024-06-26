<script lang="ts">
	export let title:string;
	export let url:string;
	export let desc:string;
    export let image:string;
	export let tech:string;
</script>

<div class="card my-2 lg:mx-1 mx-3 bg-black w-60 border-2 border-magenta rounded-lg overflow-hidden shadow-lg">
	<div class="">
		<img src={image} alt="beruang" class="object-cover w-full h-36" />
	</div>
	<div class="p-4  text-white">
		<a href={url} class=" text-base font-bold mb-2">{title}</a>
		<p class="text-[10px] mb-4">
			{desc}
		</p>
		<div class="flex space-x-2 text-xs font-semibold">
			<span class="px-2 py-1 bg-magenta text-black rounded">{tech}</span>
	</div>
	</div>
</div>
