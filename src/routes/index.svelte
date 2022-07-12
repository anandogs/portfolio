<script lang="ts">
	import Menu from '../components/Menu.svelte';

	let catPC = '/images/landing_cat.webp';
	let nerd = '/images/nerd.webp';
	let python = '/images/python_bw.webp';
	let js = '/images/js_bw.webp';
	let pandas = '/images/pandas_bw.webp';
	let flutter = '/images/flutter_bw.webp';
	let svelte_logo = '/images/svelte_bw.webp';
	let django = '/images/django_bw.webp';
	let rust = '/images/rust_bw.webp';
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

		<img src={catPC} alt="A cat in a PC" class="w-[178px]" width="178" height="178" />
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
		<img src={nerd} alt="A nerd guy" width="150.31" height="297" class="w-[150px]" />
		<div class="text-center grid gap-y-5 ">
			<Menu
				isDark={false}
				heading="Bachelor of Commerce"
				headingDetails={{
					from: 'Mumbai University',
					studied: 'Commerce',
					details: 'Accounts, Ecomomics, Commerce'
				}}
			/>
			<Menu
				isDark={false}
				heading="MBA"
				headingDetails={{
					from: 'Indian School of Business',
					studied: 'Post Graduate Program in Management',
					details: 'Finance, IT'
				}}
			/>
		</div>
	</section>
	<section class="h-screen bg-[#1D1A19] grid content-center px-[44px]" bind:this={coding}>
		<h2 class="text-center text-white">
			But at 30, I took the <span class="italic">Red Pill</span>
		</h2>
		<Capsule />

		<div class=" grid justify-items-center bg-[#1D1A19] gap-y-5">
			<Menu
				isDark={true}
				heading="Computer Science"
				headingDetails={{
					from: 'HarvardX',
					studied: 'Introduction to Computer Science',
					details: 'Scratch, C, Python'
				}}
			/>
			<Menu
				isDark={true}
				heading="Web Development"
				headingDetails={{
					from: 'HarvardX',
					studied: 'Web Programming',
					details: 'Python, Javascript'
				}}
			/>
			<Menu
				isDark={true}
				heading="UI / UX"
				headingDetails={{
					from: 'CALARTS',
					studied: 'Web Strategy & Info Architecture',
					details: 'Elements of UI & UX'
				}}
			/>
			<Menu
				isDark={true}
				heading="Machine Learning"
				headingDetails={{
					from: 'Stanford Online',
					studied: 'Machine Learning',
					details: 'Regression, Artifical Neural Nets'
				}}
			/>
		</div>
	</section>
	<section class="grainy-blue grid gap-y-11 justify-items-start py-14 px-11">
		<h2 class="text-center">Languages I <span class="italic text-white">love</span></h2>
		<div class="flex gap-[15%]">
			<img src={python} alt="Python Logo" width="100" height="100" />
			<img src={js} alt="Javascript Logo" width="100" height="100" />
		</div>
		<h2>My <span class="italic text-white">favourite</span> Frameworks and Libraries</h2>
		<div class="grid gap-y-8">
			<img src={pandas} alt="Pandas Logo" width="200" height="64.84" />
			<img src={flutter} alt="Flutter Logo" width="154" height="44" />
			<img src={svelte_logo} alt="Svelte Logo" width="200" height="37.46" />
			<img src={django} alt="Django Logo" width="200" height="69.63" />
		</div>
		<h2>Languages I'm <span class="text-white italic">geeking</span> over</h2>
		<img src={rust} alt="Rust Logo" width="100" height="100" />

	</section>
	<!-- <section class="grainy-blue grid gap-y-11">
		<h2><span class="italic text-white">Play</span> Work</h2>

	</section> -->
</main>
