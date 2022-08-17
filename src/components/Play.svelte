<script lang="ts">
	import Project from './Project.svelte';
</script>

<section class="grainy-blue grid justify-items-center justify-center" id="play">
	<h2 class="py-12"><span class="text-white italic">Play</span> Work</h2>
	<div class="grid justify-items-center justify-center md:grid-cols-2 md:gap-x-10">
		<Project
			image={'trees_of_harmony.webp'}
			imageAlt={'8 bit Picture of a boy with trees'}
			heading={'Trees of harmony'}
			text={'A Django app with a postgresql database of trees on our farm (I stay on a farm!). The farmer scans a QR code to register tree watering and I get meta data on the tree (along with life time water usage) by scanning the QR code as well.'}
			link={'https://youtu.be/O0FCYh6lzWM'}
		/>
		<Project
			image={'lilydodo.webp'}
			imageAlt={'8 bit Picture of a couple getting married'}
			heading={'dodolilywed.com'}
			text={'I made this web app for RSVPs for our wedding functions. It’s got a Gatsby front end, connected to a Firebase database and hosted on Netlify. SMS notifications were sent to people who were coming through the Twilio-Python package. Artwork done by me :)'}
			link={'https://www.dodolilywed.com'}
		/>
		<Project
			image={'solitude.webp'}
			imageAlt={'8 bit Picture of a red cow with its mouth open, running'}
			heading={'blog.solitude.farm'}
			text={'A fully functional blog on permaculture built on NextJS with Contentful as the headless CMS. A wordpress-blog-like experience through Incremental Static Regeneration (ISR) allowing bloggers to see their posts and edits as-and-when they make them. Integrated with MailChimp API for newsletter signups.'}
			link={'https://blog.solitude.farm'}
		/>
		<Project
			image={'lemiride.webp'}
			imageAlt={'8 bit Picture of a girl wearing headphones and riding a motorcycle'}
			heading={'Lemiride Mobile App'}
			text={'A Multi Platform app built using Flutter. Firebase authentication, a Django backend  along with Razorpay for payments. The app allows vendors to upload bikes and riders to rent them. Currently in internal testing on App Store and Play Store.'}
			link={''}
		/>
		<Project
			image={'breakneck.webp'}
			imageAlt={'8 bit Picture of a boy surfing a big wave'}
			heading={'breakneck.in'}
			text={'A static site built using GatsbyJS with a node-express backend. Payment integration with Razorpay. CSS using tailwind'}
			link={'https://breakneck.in'}
		/>
		<Project
			image={'tictac.webp'}
			imageAlt={'8 bit Picture of a robot playing tic tac toe'}
			heading={'Tic Tac Toe (AI)'}
			text={'A tic tac toe (knots and crosses) game built using PyGame and Python. If you beat the AI you win 500 Rupees! Recursion used to find optimal moves for the AI'}
			link={'https://youtu.be/zbjyufE-aec'}
		/>
		<Project
			image={'movies.webp'}
			imageAlt={'a crab sitting in a movie hall eating pop corn and drinking soda watching a movie 8 bit'}
			heading={'Movie Selection CLI App'}
			text={'My first CLI app using Rust. This app helps friends choose which movie to watch by borrowing from the utility maximization principle. I also wrote the code in Python'}
			link={'https://github.com/anandogs/movies_app'}
			isLast={true}
		/>
	</div>
</section>
