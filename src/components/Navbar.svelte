<script lang="ts">
	import { onMount } from 'svelte';

	let darkMode = false;

	onMount(() => {
		let boxElements = document.querySelectorAll(".toggle-dark");
		let rng = []
		for (let i = 0; i < 100; i++) {
			rng.push(i/100)
		}

		let options = {
            threshold : rng,
        }
        const handleIntersect = (enteries:any ) => {
            enteries.forEach((entry:any) => {
                if (entry.isIntersecting) {
                    if (entry.boundingClientRect.top < 40) {
                        darkMode = true
                    }
                    else {
                        darkMode = false
                    }
                }
                else {
                    darkMode = false
                }

            })
        }

        let observer = new IntersectionObserver(handleIntersect, options)
        boxElements.forEach((box:any) => {
            observer.observe(box)
        } )
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
	<div class="flex gap-x-3">
		<a href="#play" on:click|preventDefault={scrollIntoView}>
			<p class="{darkMode? "text-white":"text-black"}">• Play</p>
		</a>
		<a href="#work" on:click|preventDefault={scrollIntoView}>
		<p  class="{darkMode? "text-white":"text-black"}">• Work</p>
		</a>
	</div>
</nav>
