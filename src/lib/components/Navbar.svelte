<script>
	import NavButton from './NavButton.svelte';
</script>

<nav class="flex justify-between bg-[#191724] rounded-xl p-3 my-6">
	<div class="flex lg:justify-normal justify-center items-center">
		<NavButton to={''} title={'Home'} icon={"home"}/>
		<NavButton to={'projects'} title={'Projects'} icon={"construction"}/>
		<NavButton to={'blog'} title={'Blog'} icon={"library_books"}/>
		<NavButton to={'contacts'} title={'Contact'} icon={"contacts"}/>
	</div>
	<div class="lg:flex hidden ">
		<NavButton to={'music'} title={''} icon={"library_music"}/>
		<NavButton to={'games'} title={''} icon={"stadia_controller"}/>
	</div>
</nav>
