<script lang="ts">
	let catPC = '/images/landing_cat.png';
	let nerd = '/images/nerd.png';
	let education: HTMLElement;
	let coding: HTMLElement;
	import Navbar from '../components/Navbar.svelte';
	import IoIosArrowDown from 'svelte-icons/io/IoIosArrowDown.svelte';
	import IoIosArrowUp from 'svelte-icons/io/IoIosArrowUp.svelte';
	const scrollToLocation = (scrollLoc: HTMLElement) => {
		scrollLoc.scrollIntoView({ behavior: 'smooth', block: 'end' });
	};
</script>

<main>
	<Navbar />
	<section class="h-screen">
		<div
			class="h-[90%] pt-10 bg-[#030006] grid justify-items-center content-center px-[44px] gap-y-[3vh]"
		>
			<h1 class="text-white">Hello, World.</h1>

			<img src={catPC} alt="A cat in a PC" class="w-[178px]" />
			<h2 class="text-white text-center max-w-[278px]">
				I’m Anando - I’m interested in computers, <span class="italic">mostly</span>.
			</h2>
			<button
				class="text-white w-[25px] cursor-pointer animate-bounce pt-[3vh]"
				on:click={() => scrollToLocation(education)}
			>
				<IoIosArrowDown />
			</button>
		</div>
		<div class="h-[10%] bg-gradient-to-b from-[#030006] to-[#ECE7C2]" />
	</section>
	<section class="h-screen" bind:this={education}>
		<div
			class="h-[90%] bg-[#ECE7C2] grid justify-items-center content-center px-[44px] gap-y-[3vh]"
		>
			<h2 class="text-center">I mean I’m <span class="italic">qualified</span> for other stuff</h2>
			<img src={nerd} alt="A nerd guy" class="w-[150px]" />
			<div class="text-center grid gap-y-4">
				<div>
					<h3 class="fancy">Bachelor of Commerce</h3>
					<h3 class="">2009</h3>
				</div>
				<div>
					<h3 class="fancy">Post Graduate Program in Management</h3>
					<h3 class="">2014</h3>
				</div>
			</div>
			<button
				class="text-black w-[25px] cursor-pointer animate-bounce"
				on:click={() => scrollToLocation(coding)}
			>
				<IoIosArrowDown />
			</button>
		</div>
		<div class="h-[10%] bg-gradient-to-b from-[#ECE7C2] to-[#06010B]" />
	</section>
	<section class="h-screen" bind:this={coding}>
		<div
			class="h-[50%] bg-gradient-to-b from-[#06010B] via-[#27014C] to-[#8701B0] grid justify-items-center content-center px-[44px] gap-y-[3vh]"
		/>
		<div
			class="h-[50%] bg-gradient-to-b from-[#8701B0] via-[#FF5AA4] to-[#030006] grid justify-items-center content-center px-[44px] gap-y-[3vh]"
		/>
	</section>
</main>
