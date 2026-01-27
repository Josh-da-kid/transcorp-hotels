<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import { page } from '$app/state';

	let { children } = $props();
	let drawerOpen = $state(false);

	function closeDrawer() {
		drawerOpen = false;
	}
</script>

<svelte:head
	><link rel="icon" href="Logo - gold.png" /><title>The Metropolitan Hotel Calabar</title
	></svelte:head
>

<header class="cinzel fixed z-20 flex h-20 w-screen items-center overflow-hidden bg-zinc-800 px-8">
	<div class="flex items-center gap-5 text-amber-300">
		<img src="Logo - gold.png" alt="" class="h-8 w-9" />

		<h3>METROPOLITAN</h3>
	</div>

	<ul class="mx-auto hidden justify-center gap-10 text-amber-300 lg:flex">
		<li>HOME</li>
		<li>ROOMS & SUITES</li>
		<li>FACILITIES</li>
		<li>DINING</li>
		<li>ABOUT</li>
		<li>CONTACT</li>
	</ul>

	<div class="drawer drawer-end ml-auto w-auto lg:hidden">
		<input id="my-drawer-1" type="checkbox" class="drawer-toggle" bind:checked={drawerOpen} />
		<div class="drawer-content">
			<!-- Page content here -->
			<label for="my-drawer-1" class=""
				><svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24"
					><path
						fill="none"
						stroke="currentColor"
						stroke-linecap="round"
						stroke-width="1.5"
						d="M4 7h3m13 0h-9m9 10h-3M4 17h9m-9-5h16"
					/></svg
				></label
			>
		</div>
		<div class="drawer-side">
			<label for="my-drawer-1" aria-label="close sidebar" class="drawer-overlay"></label>
			<ul class="menu min-h-full w-80 bg-base-200 p-4">
				<!-- Sidebar content here -->

				<!-- close sidenav buton -->
				<div
					onclick={closeDrawer}
					class="mb-4 w-fit cursor-pointer"
					role="button"
					tabindex="0"
					onkeydown={(e) => e.key === 'Enter' && closeDrawer()}
				>
					<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
						><path
							fill="currentColor"
							d="m4 10l-.707.707L2.586 10l.707-.707zm17 8a1 1 0 1 1-2 0zM8.293 15.707l-5-5l1.414-1.414l5 5zm-5-6.414l5-5l1.414 1.414l-5 5zM4 9h10v2H4zm17 7v2h-2v-2zm-7-7a7 7 0 0 1 7 7h-2a5 5 0 0 0-5-5z"
						/></svg
					>
				</div>

				<li>
					<a
						href="/"
						onclick={closeDrawer}
						class={page.url.pathname === '/' ? 'text-amber-400' : 'text-gray-200'}>Home</a
					>
				</li>
				<li>
					<a
						href="/rooms-suites"
						onclick={closeDrawer}
						class={page.url.pathname === '/rooms-suites' ? 'text-amber-400' : 'text-gray-200'}
						>Rooms & Suites</a
					>
				</li>
				<li>
					<a
						href="/facilities"
						onclick={closeDrawer}
						class={page.url.pathname === '/facilities' ? 'text-amber-400' : 'text-gray-200'}
						>Facilities</a
					>
				</li>
				<li>
					<a
						href="/dining"
						onclick={closeDrawer}
						class={page.url.pathname === '/dining' ? 'text-amber-400' : 'text-gray-200'}>Dining</a
					>
				</li>
				<li>
					<a
						href="/about"
						onclick={closeDrawer}
						class={page.url.pathname === '/about' ? 'text-amber-400' : 'text-gray-200'}>About</a
					>
				</li>
				<li>
					<a
						href="/contact"
						onclick={closeDrawer}
						class={page.url.pathname === '/contact' ? 'text-amber-400' : 'text-gray-200'}>Contact</a
					>
				</li>
			</ul>
		</div>
	</div>
</header>

<main class="bg-zinc-800">
	{@render children()}
</main>

<style>
</style>
