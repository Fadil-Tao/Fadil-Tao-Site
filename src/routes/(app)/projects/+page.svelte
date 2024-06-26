<script lang="ts">
	import Frame from '$lib/components/Frame.svelte';
	import ProjectCard from '$lib/components/ProjectCard.svelte';

	type projectType = {
		title: string;
		url: string;
		desc: string;
		image: string;
		tech: string;
	};

	const projects: projectType[] = [
		{
			title: 'Coin tools',
			url: 'https://github.com/Fadil-Tao/Coin-Tools',
			desc: 'Website to display cryptocurrencies',
			image: './thumbnails/prjk1.webp',
			tech: 'React'
		},
		{
			title: 'Admin Dashboard',
			url: 'https://github.com/Fadil-Tao/DASH-PAL',
			desc: 'A simple Admin Dashboard',
			image: './thumbnails/prjk2.webp',
			tech: 'React'
		},
		{
			title: 'Growponik',
			url: 'https://github.com/Fadil-Tao/GrowPonik',
			desc: 'A site to learn about hydroponic',
			image: './thumbnails/prjk3.webp',
			tech: 'React'
		}
	];
</script>

<Frame>
	<p>Discover some of my projects</p>
	<div class="my-10 flex lg:justify-around w-full flex-wrap items-center justify-center">
		{#each projects as { title, url, desc, image, tech }}
			<ProjectCard {title} {url} {desc} {image} {tech} />
		{/each}
	</div>
	<p>To be continued ......</p>
</Frame>
