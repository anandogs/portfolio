<script lang="ts">
	import Menu from '../components/Menu.svelte';
	let catPC = '/images/landing_cat.webp';
	let nerd = '/images/nerd.webp';
	import Navbar from '../components/Navbar.svelte';
	import Capsule from '../components/Capsule.svelte';
	import Skills from '../components/Skills.svelte';
	import Play from '../components/Play.svelte';
	import Chart from '../components/Chart.svelte';
	import { onMount } from 'svelte';
	import Footer from '../components/Footer.svelte';
	let isIntersecting: boolean = false;
	onMount(() => {
		const chart = document.getElementById('myChartDiv');
		let observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						isIntersecting = true;
						return observer.unobserve(entry.target);
					}
				});
			},
			{ threshold: 1 }
		);
		if (chart) {
			observer.observe(chart);
		}
	});
</script>

<main>
	<Navbar />
	<section class="relative py-24 grid justify-items-center content-center gap-y-[5vh]">
		<div class="grainy-blue absolute w-full h-full z-[-100]" />

		<h1 class="text-white">Hello, World.</h1>

		<img src={catPC} alt="A cat in a PC" class="w-[178px]" width="178" height="178" />
		<h2 class="text-white text-center max-w-[278px]">
			I’m Anando - I’m interested in computers, <span class="italic">mostly</span>.
		</h2>
	</section>
	<section class="relative py-24 grid justify-items-center content-center gap-y-10 toggle-mode">
		<div class="grainy-brown absolute w-full h-full z-[-100]" />
		<h2 class="text-center">I thought it was a passing interest</h2>
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
	<section class="bg-[#1D1A19] py-24 grid content-center toggle-mode">
		<h2 class="text-center text-white">But at 30, I took the Red Pill</h2>
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
	<Skills />
	<Play />
	<section class="toggle-mode bg-[#1D1A19] grid justify-items-center gap-y-7 py-7" id="work">
		<h2 id="myChartDiv" class="py-12"><span class="text-white italic">Work</span> Work</h2>

		<div class="grid justify-items-center gap-y-7 md:grid-cols-2 md:gap-10 content-center">
			<p class="text-white flex items-center">
				I have been pretty much working since I graduated from college in 2009.<br /><br />
				I have a degree in Bcom and an MBA from a prestigious B-School in India.<br /><br />
				My work has been varied, but one thread that has been common since my first internship has been
				making presentations.. lots of them!<br /><br />
				Hover over the chart to get more details (or click on the bar if you're using a phone)
			</p>

			{#if isIntersecting}
				<div class="w-full">
					<Chart />
				</div>
			{/if}
		</div>

		<div class="text-white">
			<div class="grid gap-y-5 md:grid-cols-2 md:gap-x-10">
				<div class="h-[400px] grid content-center border-b border-dashed border-white ">
					<h3>Virtusa</h3>
					<p class="italic font-bold">Functional Experience: Finance</p>

					<ul class="grid gap-y-3 list-disc">
						<li>Improved Accounts Payable and Recievable Processes</li>
						<li>Managed the System Integration of financials modules of a company we acquired</li>
						<li>Helped the digital business plan and meet their financial goals</li>
						<li>Adept at working with large data sets using Python and Power Query.</li>
						<li>I dashboard through powerBi and D3/Chart.js</li>
					</ul>
				</div>
				<div class="h-[400px] grid content-center border-b border-dashed border-white ">
					<h3>Rangsutra</h3>
					<p class="italic font-bold">Functional Experience: Technology, Operations</p>

					<ul class="grid gap-y-3 list-disc">
						<li>Set up Ecommerce website using Shopify</li>
						<li>Planned delivery logistics, customer service systems and returns management</li>
					</ul>
				</div>
				<div class="h-[400px] grid content-center ">
					<h3>Fabindia</h3>
					<p class="italic font-bold">Functional Experience: Strategy, Technology</p>

					<ul class="grid gap-y-3 list-disc">
						<li>
							Corporate presentations, emails, and other communication from the Managing Directors
							office
						</li>
						<li>Worked on creating business plans for the company</li>
						<li>
							Worked on automating uploading and stock management processes for our Ecommerce site
						</li>
					</ul>
				</div>
			</div>
		</div>
	</section>
	<Footer />
</main>
