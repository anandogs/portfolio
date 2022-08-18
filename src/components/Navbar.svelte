<script lang="ts">


	function scrollIntoView({ target }: any) {
		const el = document.querySelector(target.parentElement.getAttribute('href'));
		if (!el) return;
		el.scrollIntoView({
			behavior: 'smooth'
		});
	}
</script>

<nav class="fixed top-0 w-screen py-8 px-[10%] flex justify-end z-50">
	<div class="flex gap-x-3">
		<a href="#play" on:click|preventDefault={scrollIntoView}>
			<p>• Play</p>
		</a>
		<a href="#work" on:click|preventDefault={scrollIntoView}>
		<p>• Work</p>
		</a>
	</div>
</nav>
