<script>
	import NavButton from './NavButton.svelte';
	import {IconHome,IconBook,IconHammer,IconBrandLinkedin,IconBrandX} from "@tabler/icons-svelte"
</script>

<nav class="flex justify-between bg-[#191724] rounded-xl p-3 ">
	<div class="flex lg:justify-normal justify-center items-center">
		<NavButton to={''} title={'Home'}>
			<IconHome/>
		</NavButton>
		<NavButton to={'projects'} title={'Projects'}>
			<IconHammer/>
		</NavButton>	
		<NavButton to={'blog'} title={'Blog'}>
			<IconBook/>
		</NavButton>
	</div>
	<div class="lg:flex  ">
		<NavButton to={'music'} title={''}><IconBrandLinkedin/></NavButton>
		<NavButton to={'games'} title={''}><IconBrandX/></NavButton>
	</div>
</nav>