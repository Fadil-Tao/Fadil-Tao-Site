<script lang="ts">
	import { onMount } from 'svelte';
	import {
		DropdownMenu,
		DropdownMenuItem,
		DropdownMenuLabel,
		DropdownMenuContent,
		DropdownMenuSeparator,
		DropdownMenuTrigger,
		DropdownMenuGroup
	} from '$lib/components/ui/dropdown-menu/index';
	import { IconPlaylist } from '@tabler/icons-svelte';

	import VolumeSlider from './VolumeSlider.svelte';
	import TimelineSlider from './TimelineSlider.svelte';
	import Controls from './Controls.svelte';

	let isPlaying = false;

	let volumeMuted = false;

	let volume = 0.5;

	let volumeSliderValue = 0;

	let maxVolume = 100;

	let songId = 0;

	let audioPlayer: HTMLAudioElement;

	let sliderValue = 0;

	let songLoaded = false;

	let duration: number;

	let timeline: number;

	let audioSrc: string;

	interface Audioclip {
		name: string;
		url: string;
	}

	const playlist: Audioclip[] = [
		{
			name: 'Inabakumori - Lagtrain',
			url: 'https://www.dropbox.com/scl/fi/lokl66hzr30vxixb72urg/Vo..mp3?rlkey=1znfxxxoxed6ni5gy7p25epqm&st=6llkizu9&dl=1'
		},
		{
			name: 'King Gnu - Specialz',
			url: 'https://www.dropbox.com/scl/fi/nu710vk6hf7whztgvzihx/King-Gnu-SPECIALZ.mp3?rlkey=1l7zcld3l6qmtk9zj72xnxlv6&st=ohrra70d&dl=1'
		},
		{
			name: 'Inabakumori - Lost umberella',
			url: 'https://www.dropbox.com/scl/fi/irm0315685feot3es1rxx/Vo..mp3?rlkey=oelmgaprk60xiqy1x1b0atrtz&st=byxeuzpp&dl=1'
		},
		{
			name: 'Cruel Angel Thesis',
			url: 'https://www.dropbox.com/scl/fi/d5pv31kjicyt7hwj5dhy6/MUSIC-VIDEO-HDver.-Zankoku-na-Tenshi-no-Te-ze-The-Cruel-Angel-s-Thesis.mp3?rlkey=5hjf6sr3x61pwm5dhpnqubiwh&st=d7nr9ubm&dl=1'
		}
	];

	const playPause = () => {
		if (!isPlaying) {
			audioPlayer.play();
			isPlaying = true;
		} else {
			audioPlayer.pause();
			isPlaying = false;
		}
	};

	const loadSong = () => {
		audioSrc = playlist[songId].url;
		audioPlayer.load();
		timeline = 0;
		handleLoadedAudio();
	};
	const handleLoadedAudio = () => {
		songLoaded = true;
		duration = audioPlayer.duration;
	};

	onMount(() => {
		loadSong();
	});

	const handleSliderChange = (e: Event) => {
		const target = e.target as HTMLInputElement;
		sliderValue = +target.value;
		audioPlayer.currentTime = sliderValue;
	};

	$: sliderValue = timeline;

	const switchSong = () => {
		audioPlayer.pause();
		loadSong();
		audioPlayer.play();
		isPlaying = true
	};
	const nextSong = () => {
		if (songId < playlist.length - 1) {
			songId++;
		} else {
			songId = 0;
		}
		loadSong();
		switchSong();
	};
	const prevSong = () => {
		if (songId <= 0) {
			songId = playlist.length;
		} else {
			songId -= 1;
		}
		loadSong();
		switchSong();
	};

	const jumpTo = (id: number) => {
		songId = id;
		switchSong();
	};

	const changeVolume = (volumeSliderValue) => {
		volume = volumeSliderValue / 100 

		if (volume === 0){
			volumeMuted = true
		}else {
			volumeMuted = false 
		}
	}
</script>

<div class="flex justify-between bg-[#191724] px-6 items-center rounded-lg mb-2">
	<div class="flex items-center">
		<p class="hidden md:block text-[10px] text-center">{playlist[songId].name}</p>
		<Controls {isPlaying} startSong={playPause} {nextSong} {prevSong} />
	</div>
	<TimelineSlider min={0} {songLoaded} {duration} {sliderValue} {handleSliderChange} />
	<div class="flex">
		<DropdownMenu>
			<DropdownMenuTrigger>
				<IconPlaylist />
			</DropdownMenuTrigger>
			<DropdownMenuContent>
				<DropdownMenuGroup>
					<DropdownMenuLabel>Song list</DropdownMenuLabel>
					<DropdownMenuSeparator />
					{#each playlist as { name, url }, i}
						<DropdownMenuItem>
							<button on:click={() => jumpTo(i)}>{name}</button>
						</DropdownMenuItem>
					{/each}
				</DropdownMenuGroup>
			</DropdownMenuContent>
		</DropdownMenu>
	</div>
	<VolumeSlider min={0} {volumeSliderValue} {maxVolume} {changeVolume}/>
</div>

<audio
	bind:this={audioPlayer}
	on:loadeddata={handleLoadedAudio}
	bind:duration
	bind:currentTime={timeline}
	bind:volume
	on:ended={nextSong}
>
	<source src={playlist[songId].url} />
</audio>
