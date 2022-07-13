<script lang='ts'>
    import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
    let python = '/images/python_bw.webp';
	let js = '/images/js_bw.webp';
	let pandas = '/images/pandas_bw.webp';
	let flutter = '/images/flutter_bw.webp';
	let svelte_logo = '/images/svelte_bw.webp';
	let django = '/images/django_bw.webp';
	let rust = '/images/rust_bw.webp';
    let flyClass:any;

    onMount(() => {
     const images = document.querySelectorAll('.animated-image');
     let observer = new IntersectionObserver((entries => {
        entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.toggle('flyClass')
            return observer.unobserve(entry.target);
        }
        })
     }), { threshold: .2 });
    images.forEach(image => {
        observer.observe(image);
    })
  });

</script>
<section class="grainy-blue grid gap-y-11 justify-items-start justify-center py-14 px-11">
    <h2 class="text-center">Languages I <span class="italic text-white">love</span></h2>
    <div class:flyClass class="animated-image flex gap-[15%] opacity-0">
        <img src={python} alt="Python Logo" width="100" height="100" />
        <img src={js} alt="Javascript Logo" width="100" height="100" />
        
    </div>
    <div class="w-[100%] border-b-2 border-dashed"></div>
    <h2>My <span class="italic text-white">favourite</span> Frameworks and Libraries</h2>
    <div class="grid gap-y-8">
        <img class:flyClass class="opacity-0 animated-image" src={pandas} alt="Pandas Logo" width="200" height="64.84" />
        <img class:flyClass class="opacity-0 animated-image" src={flutter} alt="Flutter Logo" width="154" height="44" />
        <img class:flyClass class="opacity-0 animated-image" src={svelte_logo} alt="Svelte Logo" width="200" height="37.46" />
        <img class:flyClass class="opacity-0 animated-image" src={django} alt="Django Logo" width="200" height="69.63" />
    </div>
    <div class="w-[100%] border-b-2 border-dashed"></div>

    <h2>Languages I'm <span class="text-white italic">geeking</span> over</h2>
    <img class:flyClass class="opacity-0 animated-image" src={rust} alt="Rust Logo" width="100" height="100" />
    <div class="w-[100%] border-b-2 border-dashed"></div>

</section>
<style>
    .flyClass {
        transform: translateY(-10px);
        opacity: 1;
        transition: 1000ms ease-in-out;
    }
</style>