<script lang="ts">
	import { page } from '$lib/title.svelte';

	page.title = 'Home - The Metropolitan Hotel Calabar';

	let current = 0;

	let leaving: number | null = null;

	const rooms = [
		{
			title: 'Standard Room',
			desc: 'Cozy comfort with modern amenities for quality stays.',
			image:
				'data:image/jpeg;base64,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'
		},
		{
			title: 'Deluxe Room',
			desc: 'Elegant space designed for premium relaxation.',
			image:
				'data:image/jpeg;base64,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'
		},
		{
			title: 'Executive Suite',
			desc: 'Luxury living with unmatched comfort and style.',
			image:
				'data:image/jpeg;base64,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'
		}
	];

	function next() {
		current = (current + 1) % rooms.length;
	}
</script>

<svelte:head><title>{page.title}</title></svelte:head>

<div class="hero mx-auto h-[500px] lg:min-h-screen" style="background-image: url(/Poolside.jpg);">
	<div class="hero-overlay"></div>

	<div class="hero-content w-full justify-start text-left text-neutral-content">
		<div class="ml-8 max-w-md lg:ml-16">
			<p class="cinzel mb-2 text-amber-300 lg:text-2xl">An Eco Travels & Tours Hotel</p>

			<h1 class="cinzel mb-5 text-3xl font-bold lg:text-6xl">METROPOLITAN HOTEL</h1>

			<p class="mb-5 lg:text-2xl">Where Atlantic Luxury Meets Nigerian Excellence</p>

			<button
				class="w-[200px] cursor-pointer rounded-lg bg-amber-500 p-3 text-sm font-medium font-semibold transition-transform duration-300 ease-in-out hover:scale-105 hover:bg-amber-600"
				>RESERVE STAY</button
			>
		</div>
	</div>
</div>

<section class="flex flex-col gap-3 px-4 py-12 text-center">
	<p class="cinzel text-amber-300">Welcome</p>
	<h2 class="cinzel text-2xl lg:text-4xl">
		EXPERIENCE <br /> CALABAR'S PREMIER <br class="hidden sm:hidden" /> DESTINATION
	</h2>
	<p class="text-gray-300">
		Experience luxury and authentic hospitality at <br /> Calabar's premier destination. <br />
		World class service, elegant rooms, exceptional <br /> dining.
	</p>

	<!-- stats section-->
	<section class="mx-auto grid w-[350px] max-w-sm grid-cols-[1fr_auto_1fr] gap-y-8 px-4 py-8">
		<div class="flex flex-col items-center justify-center">
			<svg
				class="text-amber-300"
				xmlns="http://www.w3.org/2000/svg"
				width="35"
				height="35"
				viewBox="0 0 24 24"
				><path
					fill="currentColor"
					d="M21 10.78V8c0-1.65-1.35-3-3-3h-4c-.77 0-1.47.3-2 .78c-.53-.48-1.23-.78-2-.78H6C4.35 5 3 6.35 3 8v2.78c-.61.55-1 1.34-1 2.22v6h2v-2h16v2h2v-6c0-.88-.39-1.67-1-2.22M14 7h4c.55 0 1 .45 1 1v2h-6V8c0-.55.45-1 1-1M5 8c0-.55.45-1 1-1h4c.55 0 1 .45 1 1v2H5zm-1 7v-2c0-.55.45-1 1-1h14c.55 0 1 .45 1 1v2z"
				/></svg
			>
			<p class="playfair text-3xl">130+</p>
			<p class="text-sm text-gray-400">Luxury Rooms</p>
		</div>
		<div class="flex h-full items-center justify-center">
			<div class="h-8 w-[5px] bg-amber-300"></div>
		</div>

		<div class="flex flex-col items-center justify-center">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="text-amber-300"
				width="35"
				height="35"
				viewBox="0 0 24 24"
				><path
					fill="currentColor"
					d="M12.86 10.44L11 6.06l-1.86 4.39l-4.75.41L8 14l-1.08 4.63L11 16.17l4.09 2.46L14 14l3.61-3.14zm3.73 10.26L11 17.34L5.42 20.7l1.46-6.35l-4.92-4.28l6.49-.57l2.55-6l2.55 6l6.49.57l-4.92 4.27z"
				/></svg
			>
			<p class="playfair flex items-center gap-1 text-3xl">
				4 <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
					><path
						fill="currentColor"
						d="m12 17.275l-4.15 2.5q-.275.175-.575.15t-.525-.2t-.35-.437t-.05-.588l1.1-4.725L3.775 10.8q-.25-.225-.312-.513t.037-.562t.3-.45t.55-.225l4.85-.425l1.875-4.45q.125-.3.388-.45t.537-.15t.537.15t.388.45l1.875 4.45l4.85.425q.35.05.55.225t.3.45t.038.563t-.313.512l-3.675 3.175l1.1 4.725q.075.325-.05.588t-.35.437t-.525.2t-.575-.15z"
					/></svg
				>
			</p>
			<p class="text-sm text-gray-400">Guest Rated</p>
		</div>

		<div class="flex flex-col items-center justify-center">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="text-amber-300"
				width="35"
				height="35"
				viewBox="0 0 24 24"
				><g
					><path fill="currentColor" d="M7 3H17V7.2L12 12L7 7.2V3Z"
						><animate
							id="SVGFjnOndxt"
							fill="freeze"
							attributeName="opacity"
							begin="0;SVGn6mLadge.end"
							dur="2s"
							from="1"
							to="0"
						/></path
					><path fill="currentColor" d="M17 21H7V16.8L12 12L17 16.8V21Z"
						><animate
							fill="freeze"
							attributeName="opacity"
							begin="0;SVGn6mLadge.end"
							dur="2s"
							from="0"
							to="1"
						/></path
					><path
						fill="currentColor"
						d="M6 2V8H6.01L6 8.01L10 12L6 16L6.01 16.01H6V22H18V16.01H17.99L18 16L14 12L18 8.01L17.99 8H18V2H6ZM16 16.5V20H8V16.5L12 12.5L16 16.5ZM12 11.5L8 7.5V4H16V7.5L12 11.5Z"
					/><animateTransform
						id="SVGn6mLadge"
						attributeName="transform"
						attributeType="XML"
						begin="SVGFjnOndxt.end"
						dur="0.5s"
						from="0 12 12"
						to="180 12 12"
						type="rotate"
					/></g
				></svg
			>
			<p class="playfair text-3xl">15+</p>
			<p class="text-sm text-gray-400">Years of Excellence</p>
		</div>
		<div class="flex h-full items-center justify-center">
			<div class="h-8 w-[5px] bg-amber-300"></div>
		</div>

		<div class="flex flex-col items-center justify-center">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="text-amber-300"
				width="35"
				height="35"
				viewBox="0 0 16 16"
				><path fill="currentColor" d="m5 0l2.075 4.565A6.5 6.5 0 0 0 3.073 6.76L0 0z" /><path
					fill="currentColor"
					fill-rule="evenodd"
					d="M7.73 6.007A4.997 4.997 0 0 0 3 11a5 5 0 1 0 9.22-2.683L16 0h-5L8.27 6.007a5 5 0 0 0-.54 0M9.25 11a1.25 1.25 0 1 1-2.5 0a1.25 1.25 0 0 1 2.5 0"
					clip-rule="evenodd"
				/></svg
			>
			<p class="playfair text-3xl">AWARD</p>
			<p class="text-sm text-gray-400">Winning Hotel</p>
		</div>
	</section>
</section>

<!-- accomodation -->
<section class="flex flex-col gap-3 px-4 py-12 text-center">
	<p class="cinzel text-amber-300">Accomodation</p>

	<section class="relative overflow-hidden bg-gradient-to-b from-zinc-900 to-zinc-950 py-20">
		<div class="mx-auto flex max-w-6xl gap-6 px-6">
			<!-- LEFT CONTENT -->
			<div class="w-[40%] pt-10 text-white">
				<span class="mb-4 block h-[2px] w-8 bg-amber-400"></span>

				<h3 class="cinzel mb-4 text-2xl">
					{rooms[current].title}
				</h3>

				<p class="mb-6 text-sm text-zinc-400">
					{rooms[current].desc}
				</p>

				<button
					class="rounded-full bg-gradient-to-r from-amber-300 to-amber-500 px-6 py-2 text-sm font-medium text-black"
				>
					Explore Room
				</button>
			</div>

			<!-- IMAGE RAIL -->
			<div class="relative w-[60%] overflow-hidden">
				<div
					class="flex gap-6 transition-transform duration-500 ease-out"
					style="transform: translateX(-{current * 70}%);"
				>
					{#each rooms as room, i}
						<div
							class="relative w-[70%] shrink-0 transition-all duration-500"
							style={i === current
								? 'transform: perspective(1000px) rotateY(-10deg); transform-origin: left center;'
								: ''}
						>
							<img
								src={room.image}
								alt={room.title}
								class="h-[420px] w-full rounded-2xl object-cover"
							/>

							<!-- Darken non-active -->
							{#if i !== current}
								<div class="absolute inset-0 rounded-2xl h-[200px                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       ] bg-black/50"></div>
							{/if}
						</div>
					{/each}
				</div>
			</div>
		</div>

		<!-- Next Button (hidden but functional / optional UI) -->
		<button on:click={next} class="absolute top-1/2 right-6 -translate-y-1/2 text-amber-400">
			→
		</button>
	</section>
</section>
