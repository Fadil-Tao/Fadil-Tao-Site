<script lang="ts">
	import {
		DropdownMenu,
		DropdownMenuItem,
		DropdownMenuLabel,
		DropdownMenuContent,
		DropdownMenuSeparator,
		DropdownMenuTrigger,
		DropdownMenuGroup
	} from '$lib/components/ui/dropdown-menu/index';
</script>

<div class="flex justify-between bg-[#191724] px-6 items-center">
	<div class="flex ">
		<p>song name</p>
		<div class="flex">
			<div>
				{'<'}
			</div>
			<div>
                
			</div>
			<div>
				{'>'}
			</div>
		</div>
	</div>
	<div class=" bg-amber-200 lg:w-1/2">
		<input type="range" min="0" value="0" class="w-full" />
	</div>
	<div class="flex">
		<DropdownMenu>
			<DropdownMenuTrigger>
				<div class="flex items-center">
					<span class="material-symbols-outlined"> playlist_play </span>
				</div>
			</DropdownMenuTrigger>
			<DropdownMenuContent>
				<DropdownMenuGroup>
					<DropdownMenuLabel>Song list</DropdownMenuLabel>
					<DropdownMenuSeparator />
					<DropdownMenuItem>Profile</DropdownMenuItem>
					<DropdownMenuItem>Billing</DropdownMenuItem>
					<DropdownMenuItem>Team</DropdownMenuItem>
					<DropdownMenuItem>Subscription</DropdownMenuItem>
				</DropdownMenuGroup>
			</DropdownMenuContent>
		</DropdownMenu>
		<div class="flex items-center">
			<div class="flex items-center">
				<span class="material-symbols-outlined"> volume_up </span>
			</div>
			<input type="range" min="0" value="0" class="w-full" />
		</div>
	</div>
</div>
