<script lang="ts">
	import Menu from '../components/Menu.svelte';
	
	let catPC = '/images/landing_cat.png';
	let nerd = '/images/nerd.png';
	let education: HTMLElement;
	let coding: HTMLElement;
	import Navbar from '../components/Navbar.svelte';
	import Capsule from '../components/Capsule.svelte';
	
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
	</section>
	<section
		class="relative h-screen grid justify-items-center content-center px-[44px] gap-y-10"
		bind:this={education}
	>
		<div class="grainy-brown absolute w-screen h-screen z-[-100]" />
		<h2 class="text-center">I <span class="italic">thought</span> it was a passing interest</h2>
		<img src={nerd} alt="A nerd guy" class="w-[150px]" />
		<div class="text-center grid gap-y-5 ">
			<Menu isDark={false} heading='Bachelor of Commerce' headingDetails={{from: 'Mumbai University', studied: 'Commerce', details: 'Accounts, Ecomomics, Commerce'}}/>
			<Menu isDark={false} heading='MBA' headingDetails={{from: 'Indian School of Business', studied: 'Post Graduate Program in Management', details: 'Finance, IT'}}/>
		</div>
	</section>
	<section class="h-screen bg-[#1D1A19] grid content-center px-[44px]" bind:this={coding}>
		
			<h2 class="text-center text-white">
				But at 30, I took the <span class="italic">Red Pill</span>
			</h2>
			<Capsule />

		<div class=" grid justify-items-center bg-[#1D1A19] gap-y-5">
			<Menu isDark={true} heading='Computer Science' headingDetails={{from: 'HarvardX', studied: 'Introduction to Computer Science', details: 'Scratch, C, Python'}}/>
			<Menu isDark={true} heading='Web Development' headingDetails={{from: 'HarvardX', studied: 'Web Programming', details: 'Python, Javascript'}}/>
			<Menu isDark={true} heading='UI / UX' headingDetails={{from: 'CALARTS', studied: 'Web Strategy & Info Architecture', details: 'Elements of UI & UX'}}/>
			<Menu isDark={true} heading='Machine Learning' headingDetails={{from: 'Stanford Online', studied: 'Machine Learning', details: 'Regression, Artifical Neural Nets'}}/>
		</div>
	</section>
</main>
