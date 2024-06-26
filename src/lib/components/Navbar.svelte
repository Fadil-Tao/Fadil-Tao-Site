<script>
	import NavButton from './NavButton.svelte';
</script>

<nav class="flex justify-between bg-[#191724] rounded-xl p-3 ">
	<div class="flex lg:justify-normal justify-center items-center">
		<NavButton to={''} title={'Home'}>
		<NavButton to={'projects'} title={'Projects'} />	
		<NavButton to={'blog'} title={'Blog'}/>
	</div>
	<div class="lg:flex hidden ">
		<NavButton to={'music'} title={''} />
		<NavButton to={'games'} title={''}/>
	</div>
</nav>
