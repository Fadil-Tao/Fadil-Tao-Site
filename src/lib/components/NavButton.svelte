<script lang="ts">
	import { page } from '$app/stores';
	export let to: string;
	export let title: string;
</script>

<div>
	<div
		class={`flex justify-center items-center border-plum mx-2 md:mx-6 hover:text-plum ${$page.url.pathname === `/${to}` ? ' text-plum border-b-2' : ''}`}
	>
		<a href={`/${to}`} class="flex justify-center items-center md:items-start md:text-lg text-xs">
			<div class="block"><slot /></div>
			{title}
		</a>
	</div>
</div>
