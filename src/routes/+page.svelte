<script lang="ts">
	import { page } from '$lib/title.svelte';

	page.title = 'Home - The Metropolitan Hotel Calabar';
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

	<section class="flex flex-col gap-8 px-4 py-8">
		<div class="mx-auto flex max-w-sm items-center justify-between gap-15">
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
			<div class="h-11 w-[3px] bg-amber-300"></div>

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
		</div>

		<div class="mx-auto flex max-w-sm items-center justify-between gap-15">
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
			<div class="h-11 w-[3px] bg-amber-300"></div>

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
		</div>
	</section>
</section>
