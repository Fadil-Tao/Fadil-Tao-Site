<script>
	import NavButton from './NavButton.svelte';
	import {
		IconHome,
		IconBook,
		IconHammer,
		IconBrandLinkedin,
		IconBrandGithub
	} from '@tabler/icons-svelte';
</script>

<nav class="flex justify-between bg-[#191724] rounded-xl p-3">
	<div class="flex lg:justify-normal justify-center items-center">
		<NavButton to={''} title={'Home'}>
			<div class=" md:block hidden">
				<IconHome />
			</div>
		</NavButton>
		<NavButton to={'projects'} title={'Projects'}>
			<div class=" md:block hidden">
				<IconHammer />
			</div>
		</NavButton>
		<NavButton to={'blog'} title={'Blog'}>
			<div class=" md:block hidden">
				<IconBook />
			</div>
		</NavButton>
	</div>
	<div class="md:flex">
		<NavButton to={'https://www.linkedin.com/in/hadad-fadilah234/'} title={''}
			> <IconBrandLinkedin /></NavButton
		>
		<NavButton to={'https://github.com/Fadil-Tao'} title={''}><IconBrandGithub /></NavButton>
	</div>
</nav>
