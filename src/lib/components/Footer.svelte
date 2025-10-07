<script lang="ts">
	const currentYear = new Date().getFullYear();
	
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
	
	const footerLinks = {
		navigation: [
			{ label: 'Home', href: '/' },
			{ label: 'Work History', href: '/work-history', onclick: scrollToWorkHistory },
			{ label: 'Demo Projects', href: '/demo-projects', onclick: scrollToDemoProjects },
			{ label: 'Svelte Projects', href: '/svelte-projects', onclick: scrollToSvelteProjects }
		] as NavItem[],
		social: [
			{ label: 'GitHub', href: 'https://github.com/devmarked', icon: 'github' },
			{ label: 'X', href: 'https://x.com/markedcarlo', icon: 'twitter' },
			{ label: 'LinkedIn', href: 'https://linkedin.com/mclumbayan', icon: 'linkedin' },
			{ label: 'Youtube', href: 'https://www.youtube.com/@MarkDev-jw9zs', icon: 'youtube' },
			{ label: 'Email', href: 'mailto:markedcarlo@gmail.com', icon: 'email' },

		]
	};
</script>

<footer class="border-t border-gray-200 bg-white">
	<div class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
		<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
			<!-- Brand -->
			<div class="space-y-4">
				<h3 class="text-xl font-bold text-gray-900">
					<span class="text-blue-600">Svelte</span>Journey
				</h3>
				<p class="text-md text-gray-600">
					Documenting my journey learning Svelte, from simple projects to complex applications.
				</p>
			</div>

			<!-- Navigation Links -->
			<div class="space-y-4">
				<h4 class="text-md font-semibold uppercase tracking-wider text-gray-900">Navigation</h4>
				<ul class="space-y-2">
					{#each footerLinks.navigation as link}
						<li>
							<a
								href={link.href}
								class="text-md text-gray-600 hover:text-blue-600 transition-colors"
								onclick={link.onclick}
							>
								{link.label}
							</a>
						</li>
					{/each}
				</ul>
			</div>

			<!-- Social Links -->
			<div class="space-y-4">
				<h4 class="text-md font-semibold uppercase tracking-wider text-gray-900">Connect</h4>
				<div class="flex space-x-4">
					{#each footerLinks.social as social}
						<a
							href={social.href}
							target="_blank"
							rel="noopener noreferrer"
							class="text-gray-600 hover:text-blue-600 transition-colors"
							aria-label={social.label}
						>
							{#if social.icon === 'github'}
								<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
									<path
										fill-rule="evenodd"
										d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
										clip-rule="evenodd"
									/>
								</svg>
							{:else if social.icon === 'twitter'}
								<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
									<path
										d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"
									/>
								</svg>
							{:else if social.icon === 'linkedin'}
								<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
									<path
										d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
									/>
								</svg>
							{:else if social.icon === 'youtube'}
								<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
									<path
										d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"
									/>
								</svg>
							{:else if social.icon === 'email'}
								<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24">
									<path
										d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"
									/>
								</svg>
							{/if}
						</a>
					{/each}
				</div>
			</div>
		</div>

		<!-- Bottom bar -->
		<div class="mt-8 border-t border-gray-200 pt-8">
			<p class="text-center text-md text-gray-600">
				© {currentYear} MarkCarlo. Built with SvelteKit and Tailwind CSS.
			</p>
		</div>
	</div>
</footer>

