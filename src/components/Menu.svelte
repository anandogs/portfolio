<script lang="ts">
	export let heading: string;
	export let headingDetails: {
		from: string;
		studied: string;
		details: string;
	};
    export let isDark:boolean;

	let showMenu = false;
	const toggleShowMenu = () => {
		showMenu = !showMenu;
	};
	import IoIosArrowDown from 'svelte-icons/io/IoIosArrowDown.svelte';
	import IoIosClose from 'svelte-icons/io/IoIosClose.svelte';
	import { fly } from 'svelte/transition';
</script>

<div
	class={`w-[250px] transition-height ${
		showMenu ? 'h-[140px]' : 'h-[33px]'
	} duration-500 ease-in-out ${isDark? 'border-white': 'border-[#1D1A19]'}  border-b border-l border-r z-10`}
>
	<button class="flex justify-between px-5 cursor-pointer w-[100%]"  on:click={toggleShowMenu}>
		<p class={isDark? 'text-white': 'text-[#1D1A19]'}>{heading}</p>
		<div class={`${isDark?'text-white': 'text-[#1D1A19]'} w-[25px]`}>
			{#if showMenu}
				<IoIosClose />
			{:else}
				<IoIosArrowDown />
			{/if}
        </div>
	</button>
	{#if showMenu}
		<div transition:fly={{ y:-10, duration:500 }} class={`${isDark ? 'text-white': 'text-[#1D1A19]'} pt-2 grid gap-y-2`}>
			<div class="flex justify-center menu ">{headingDetails.from}</div>
			<div class="flex justify-center menu">{headingDetails.studied}</div>
			<div class="flex justify-center menu">{headingDetails.details}</div>
		</div>
	{/if}
</div>
