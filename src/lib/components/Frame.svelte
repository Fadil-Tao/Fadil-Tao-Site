<script>
	import { page } from '$app/stores';
</script>

<div class="border-magenta border-[1.5px] border-opacity-80 bg-black bg-opacity-80">
	<div class="framehead flex items-center justify-between lg:px-9 md:px-8 px-5 py-[3px] text-white">
		<div class="flex lg:items-start items-end">
			<img src="./icons/folder.webp" alt="" class="h-[20px] mr-2">
			<p class="md:text-base text-xs">{`C:/HADAD${$page.url.pathname.toUpperCase()}`}</p>
		</div>
		<div class="flex">
			<div class="w-4 ml-1 h-4 bg-[#F6D013] rounded-full"></div>
			<div class="w-4 ml-1 h-4 bg-[#128791] rounded-full"></div>
			<div class="w-4 ml-1 h-4 bg-[#FA4B47] rounded-full"></div>
		</div>
	</div>
	<div class="framebody lg:px-10 md:px-8 px-5 flex flex-col justify-center items-center py-5">
	 	<slot/>
	</div>
</div>

<style>
	.framehead {
		background: rgb(201, 15, 186);
		background: linear-gradient(90deg, rgba(201, 15, 186, 1) 0%, rgba(104, 37, 190, 1) 100%);
	}
</style>
