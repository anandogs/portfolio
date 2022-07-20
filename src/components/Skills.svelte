<script lang="ts">
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	let python = '/images/python_bw.webp';
	let js = '/images/js_bw.webp';
	let pandas = '/images/pandas_bw.webp';
	let flutter = '/images/flutter_bw.webp';
	let svelte_logo = '/images/svelte_bw.webp';
	let django = '/images/django_bw.webp';
	let rust = '/images/rust_bw.webp';
	let flyClass: any;

	onMount(() => {
		const images = document.querySelectorAll('.animated-image');
		let observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						entry.target.classList.toggle('flyClass');
						return observer.unobserve(entry.target);
					}
				});
			},
			{ threshold: 0.2 }
		);
		images.forEach((image) => {
			observer.observe(image);
		});
	});
</script>

<section class="grainy-blue grid gap-y-8 justify-items-center justify-center py-14">
	<h2 class="text-center">Languages I <span class="italic text-white">love</span></h2>
	<div class:flyClass class="animated-image flex gap-[15%] justify-center opacity-0">
		<img src={python} alt="Python Logo" width="50" height="50" />
		<img src={js} alt="Javascript Logo" width="50" height="50" />
	</div>
	<div class="w-[100%] border-b border-dashed" />
	<h3 class="text-white">My favourite Frameworks and Libraries</h3>
	<div class="flex gap-x-7">
		<div class="grid gap-y-2">
			<img
				class:flyClass
				class="opacity-0 animated-image"
				src={pandas}
				alt="Pandas Logo"
				width="115"
				height="37"
			/>
			<img
				class:flyClass
				class="opacity-0 animated-image"
				src={flutter}
				alt="Flutter Logo"
				width="102"
				height="29"
			/>
		</div>
		<div class="grid gap-y-6 items-center">
			<img
				class:flyClass
				class="opacity-0 animated-image"
				src={svelte_logo}
				alt="Svelte Logo"
				width="106"
				height="19"
			/>
			<img
				class:flyClass
				class="opacity-0 animated-image"
				src={django}
				alt="Django Logo"
				width="88"
				height="31"
			/>
		</div>
	</div>
	<div class="w-[100%] border-b border-dashed" />

	<h3 class="text-white">Languages I'm geeking over</h3>
	<img
		class:flyClass
		class="opacity-0 animated-image"
		src={rust}
		alt="Rust Logo"
		width="72"
		height="72"
	/>
	<div class="w-[100%] border-b border-dashed" />
</section>

<style>
	.flyClass {
		transform: translateY(-10px);
		opacity: 1;
		transition: 1000ms ease-in-out;
	}
</style>
