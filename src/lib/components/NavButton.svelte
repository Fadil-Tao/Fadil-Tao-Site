<script lang="ts"> 
    import {page} from "$app/stores"
    export let to:string ;
    export let title:string ;   
    export let icon:string;
</script>

<div>
    <div class={`flex justify-center items-center border-plum mx-2 md:mx-6 ${$page.url.pathname === `/${to}` ? " text-plum border-b-2": ""}`}>
        <a href={`/${to}`} class="flex justify-center items-start md:text-lg text-xs ">
			<span class="material-symbols-outlined md:block hidden"> {icon} </span>
            {title}
        </a>
	</div>
</div>