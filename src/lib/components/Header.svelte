<script lang="ts">
	import { page } from '$app/stores';

	let mobileMenuOpen = $state(false);

	// Smooth scroll to work history section
	function scrollToWorkHistory(e: MouseEvent) {
		e.preventDefault();
		const element = document.getElementById('work-history');
		element?.scrollIntoView({ behavior: 'smooth' });
	}

	// Smooth scroll to demo projects section
	function scrollToDemoProjects(e: MouseEvent) {
		e.preventDefault();
		const element = document.getElementById('demo-projects');
		element?.scrollIntoView({ behavior: 'smooth' });
	}

	// Smooth scroll to svelte projects section
	function scrollToSvelteProjects(e: MouseEvent) {
		e.preventDefault();
		const element = document.getElementById('svelte-projects');
		element?.scrollIntoView({ behavior: 'smooth' });
	}

	interface NavItem {
		label: string;
		href: string;
		onclick?: (e: MouseEvent) => void;
	}

	const navItems: NavItem[] = [
		{ label: 'Home', href: '/' },
		{ label: 'Work History', href: '/work-history', onclick: scrollToWorkHistory },
		{ label: 'Demo Projects', href: '/demo-projects', onclick: scrollToDemoProjects },
		{ label: 'Svelte Projects', href: '/svelte-projects', onclick: scrollToSvelteProjects }
	];
</script>

<header class="fixed top-0 z-50 w-full border-b border-gray-200 bg-white/80 backdrop-blur-lg">
	<nav class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<!-- Logo -->
			<div class="flex items-center">
				<a href="/" class="text-2xl font-bold text-gray-900 transition-colors">
					<span class="text-orange-500">Mark</span>Carlo
				</a>
			</div>

			<!-- Desktop Navigation -->
			<div class="hidden md:flex md:items-center md:space-x-8">
				{#each navItems as item}
					<a
						href={item.href}
						class="text-md font-medium text-gray-700 transition-colors hover:text-orange-500"
						onclick={item.onclick}
					>
						{item.label}
					</a>
				{/each}
			</div>

			<!-- Mobile menu button -->
			<div class="md:hidden">
				<button
					onclick={() => (mobileMenuOpen = !mobileMenuOpen)}
					class="inline-flex items-center justify-center rounded-md p-2 text-gray-700 hover:bg-gray-100 hover:text-blue-600"
					aria-label="Toggle menu"
				>
					<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
						{#if mobileMenuOpen}
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M6 18L18 6M6 6l12 12"
							/>
						{:else}
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M4 6h16M4 12h16M4 18h16"
							/>
						{/if}
					</svg>
				</button>
			</div>
		</div>

		<!-- Mobile menu -->
		{#if mobileMenuOpen}
			<div class="border-t border-gray-200 pt-4 pb-4 md:hidden">
				<div class="space-y-1">
					{#each navItems as item}
						<a
							href={item.href}
							class="block rounded-md px-3 py-2 text-base font-medium text-gray-700 hover:bg-gray-50 hover:text-blue-600"
							onclick={(e) => {
								item.onclick?.(e);
								mobileMenuOpen = false;
							}}
						>
							{item.label}
						</a>
					{/each}
				</div>
			</div>
		{/if}
	</nav>
</header>
