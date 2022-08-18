<script lang="ts">
	import { onMount } from 'svelte';

	let darkMode = false;

	onMount(() => {
		const sectionsToToggle = document.querySelectorAll('.toggle-mode');

		let observer = new IntersectionObserver(
			(entries) => {
				console.log(entries)
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						darkMode = !darkMode;

					}
					else {
						console.log(entry)
					}
				});
			},
			{ threshold: 0.9 }
		);
		sectionsToToggle.forEach((section) => {
			observer.observe(section);
		});
	});


	function scrollIntoView({ target }: any) {
		const el = document.querySelector(target.parentElement.getAttribute('href'));
		if (!el) return;
		el.scrollIntoView({
			behavior: 'smooth'
		});
	}
</script>

<nav class="fixed top-0 w-screen py-8 px-[10%] flex justify-end z-50">
	<div class="{darkMode? "text-white":"text-black"} flex gap-x-3">
		<a href="#play" on:click|preventDefault={scrollIntoView}>
			<p>• Play</p>
		</a>
		<a href="#work" on:click|preventDefault={scrollIntoView}>
			<p>• Work</p>
		</a>
	</div>
</nav>
