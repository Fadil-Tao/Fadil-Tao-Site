<script>
	import TechBigIcon from './TechBigIcon.svelte';
</script>

<div class="rounded-full h-40 w-40">
	<img
		src="./favicon.png"
		alt="profile img"
		class="object-contain rounded-full"
	/>
</div>
<div class=" text-center">
	<p class=" text-3xl">HI! I'M <span class="text-plum font-bold">HADAD</span></p>
	<p class=" text-sm my-5">Frontend Web Developer</p>
	<div class="md:text-justify ">
		<p class="text-plum font-bold">About Me</p>
		<p>
			Im a frontend developer and currently computer science student at Institut Teknologi
			Kalimantan. Im currently focusing on learning more about Javascript , Typescript and GO . I
			have quiet experience in frontend development using react and svelte. i also developing my
			skills in backend using go programming language
		</p>
	</div>
	<div class="mt-10">
		<p>Experienced in these tech :</p>
		<div class="flex md:justify-around flex-wrap">
			<TechBigIcon
				img="./icons/technologies/react.webp"
				title="React"
			/>
            <TechBigIcon
                img="./icons/technologies/svelte.webp"
                title="Svelte"
            />
			<TechBigIcon
				img="./icons/technologies/golang.webp"
				title="Golang"
			/>
			<TechBigIcon
				img="./icons/technologies/docker.webp"
				title="Docker"
			/>
			<TechBigIcon
				img="./icons/technologies/postgresql.webp"
				title="PostgresQL"
			/>
			<TechBigIcon
				img="./icons/technologies/JavaScript.webp"
				title="Javascript"
			/>
		</div>
	</div>
</div>
