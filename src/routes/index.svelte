<script lang="ts">
	let catPC = '/images/landing_cat.png';
	let nerd = '/images/nerd.png';
	let education: HTMLElement;
	let coding: HTMLElement;
	import Navbar from '../components/Navbar.svelte';
	import IoIosArrowDown from 'svelte-icons/io/IoIosArrowDown.svelte';
	import Capsule from '../components/Capsule.svelte';
	const scrollToLocation = (scrollLoc: HTMLElement) => {
		scrollLoc.scrollIntoView({ behavior: 'smooth', block: 'end' });
	};
</script>

<main>
	<Navbar />
	<section
		class="relative h-screen pt-10 grid justify-items-center content-center px-[44px] gap-y-[5vh]"
	>
		<div class="grainy-blue absolute w-screen h-screen z-[-100]" />

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
	</section>
	<section
		class="relative h-screen grid justify-items-center content-center px-[44px] gap-y-[2vh]"
		bind:this={education}
	>
		<div class="grainy-brown absolute w-screen h-screen z-[-100]" />
		<h2 class="text-center">I mean I’m <span class="italic">qualified</span> for other stuff</h2>
		<img src={nerd} alt="A nerd guy" class="w-[150px]" />
		<div class="text-center grid gap-y-1">
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
	</section>
	<section class="h-screen bg-[#1D1A19] " bind:this={coding}>
		<Capsule />

		<div class="h-[45%]">
			<h2 class="text-center px-[44px] pt-[20%] text-white">
				But I'm <span class="italic">passionate</span> about code.
			</h2>
		</div>
		<div class="h-[50%] grid justify-items-center">
			<div class="w-[250px] h-[33px] flex justify-evenly border-white border-b border-l border-r">
				<p class="text-white">Computer Science

				</p>
				<button
				class="text-white w-[25px] cursor-pointer"
			>
				<IoIosArrowDown />
			</button>
			</div>
			<!-- <h2 class="text-center px-[44px] text-white">Hi.</h2> -->
		</div>
	</section>
</main>
