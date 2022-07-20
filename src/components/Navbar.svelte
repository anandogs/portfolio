<script lang="ts">
	function scrollIntoView({ target }: any) {
		const el = document.querySelector(target.parentElement.getAttribute('href'));
		if (!el) return;
		el.scrollIntoView({
			behavior: 'smooth'
		});
	}
	let playPressed = false;
</script>

<nav class="fixed top-0 w-screen py-8 px-[10%] flex justify-end z-50">
	<div class="flex gap-x-3">
		<a
			href="#play"
			on:click={() => (playPressed = !playPressed)}
			on:click|preventDefault={scrollIntoView}
		>
			<p class={playPressed ? 'text-white border-b border-dashed' : ''}>• Play</p>
		</a>
		<p>• Work</p>
	</div>
</nav>

<!-- -->
