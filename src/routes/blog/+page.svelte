<script lang="ts">
	// Coming Soon page for blog
</script>

<svelte:head>
	<title>Blog - Coming Soon</title>
	<meta name="description" content="Blog coming soon - stay tuned for articles about web development, Svelte, and more!" />
</svelte:head>

<div class="min-h-[calc(100vh-200px)] bg-gradient-to-b from-white to-gray-50">
	<div class="mx-auto max-w-4xl px-4 py-16 sm:px-6 sm:py-24 lg:px-8">
		<!-- Main Content -->
		<div class="text-center">
		<!-- Icon/Illustration -->
		<div class="mx-auto mb-8 flex h-24 w-24 items-center justify-center rounded-full bg-orange-100">
			<svg
				class="h-12 w-12 text-orange-500"
					fill="none"
					stroke="currentColor"
					viewBox="0 0 24 24"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"
					/>
				</svg>
			</div>

			<!-- Heading -->
			<h1 class="text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl md:text-6xl">
				Blog Coming Soon
			</h1>

			<!-- Description -->
			<p class="mx-auto mt-6 max-w-2xl text-lg leading-8 text-gray-600 sm:text-xl">
				I'm currently working on creating valuable content about web development, SvelteKit, best
				practices, and my learning journey. Stay tuned for insightful articles and tutorials!
			</p>

			<!-- Feature List -->
			<div class="mx-auto mt-12 max-w-2xl">
			<div class="grid gap-6 sm:grid-cols-2">
				<div class="rounded-lg bg-white p-6 shadow-sm ring-1 ring-gray-200">
					<div class="mb-3 flex h-10 w-10 items-center justify-center rounded-lg bg-orange-50">
						<svg
							class="h-6 w-6 text-orange-500"
							fill="none"
							stroke="currentColor"
							viewBox="0 0 24 24"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
							/>
						</svg>
					</div>
					<h3 class="text-left text-lg font-semibold text-gray-900">Code Tutorials</h3>
						<p class="mt-2 text-left text-sm text-gray-600">
							Step-by-step guides on building with SvelteKit and modern web technologies
						</p>
					</div>

				<div class="rounded-lg bg-white p-6 shadow-sm ring-1 ring-gray-200">
					<div class="mb-3 flex h-10 w-10 items-center justify-center rounded-lg bg-orange-50">
						<svg
							class="h-6 w-6 text-orange-500"
							fill="none"
							stroke="currentColor"
							viewBox="0 0 24 24"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"
							/>
						</svg>
					</div>
					<h3 class="text-left text-lg font-semibold text-gray-900">Best Practices</h3>
						<p class="mt-2 text-left text-sm text-gray-600">
							Insights and patterns learned from real-world projects
						</p>
					</div>

				<div class="rounded-lg bg-white p-6 shadow-sm ring-1 ring-gray-200">
					<div class="mb-3 flex h-10 w-10 items-center justify-center rounded-lg bg-orange-50">
						<svg
							class="h-6 w-6 text-orange-500"
							fill="none"
							stroke="currentColor"
							viewBox="0 0 24 24"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M13 10V3L4 14h7v7l9-11h-7z"
							/>
						</svg>
					</div>
					<h3 class="text-left text-lg font-semibold text-gray-900">Quick Tips</h3>
						<p class="mt-2 text-left text-sm text-gray-600">
							Short, actionable tips to improve your development workflow
						</p>
					</div>

				<div class="rounded-lg bg-white p-6 shadow-sm ring-1 ring-gray-200">
					<div class="mb-3 flex h-10 w-10 items-center justify-center rounded-lg bg-orange-50">
						<svg
							class="h-6 w-6 text-orange-500"
							fill="none"
							stroke="currentColor"
							viewBox="0 0 24 24"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
							/>
						</svg>
					</div>
					<h3 class="text-left text-lg font-semibold text-gray-900">Learning Journey</h3>
						<p class="mt-2 text-left text-sm text-gray-600">
							Personal experiences and lessons learned throughout my development path
						</p>
					</div>
				</div>
			</div>

		<!-- CTA Section -->
		<div class="mt-16">
			<div class="rounded-2xl bg-orange-50 px-6 py-8 sm:px-12">
				<h3 class="text-xl font-semibold text-gray-900">Want to be notified?</h3>
				<p class="mt-2 text-gray-600">
					In the meantime, check out my projects to see what I've been building!
				</p>
				<div class="mt-6">
					<a
						href="/"
						class="inline-flex items-center rounded-lg bg-orange-500 px-6 py-3 text-base font-semibold text-white shadow-sm transition-colors hover:bg-orange-600 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2"
						>
							View Projects
							<svg
								class="ml-2 h-5 w-5"
								fill="none"
								stroke="currentColor"
								viewBox="0 0 24 24"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M13 7l5 5m0 0l-5 5m5-5H6"
								/>
							</svg>
						</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

