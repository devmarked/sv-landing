<script lang="ts">
	import { fade, fly, scale } from 'svelte/transition';
	import { onMount } from 'svelte';
	import HeroImage from '$lib/assets/hero-lg.png';

	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});

	// Smooth scroll to demo projects section
	function scrollToProjects(e: MouseEvent) {
		e.preventDefault();
		const element = document.getElementById('demo-projects');
		element?.scrollIntoView({ behavior: 'smooth' });
	}
</script>

<section class="relative overflow-hidden pt-24 pb-16 font-sans">
	<!-- Background decoration -->
	<div class="absolute inset-0 -z-10">
		<div class="absolute top-0 left-1/2 -translate-x-1/2 blur-3xl">
			<div class="aspect-[1155/678] w-[72.1875rem]"></div>
		</div>
	</div>

	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="grid items-center gap-12 lg:grid-cols-2 lg:gap-16">
			<!-- Right Column - Text Content -->
			<div class="order-2 lg:order-1">
				{#if mounted}
					<!-- Badge -->
					<div
						in:fly={{ y: -20, duration: 600, delay: 100 }}
						class="mb-6 inline-flex items-center rounded-full border border-blue-200 bg-blue-50 px-4 py-1.5 text-sm font-medium text-blue-700"
					>
						<span class="mr-2">🚀</span>
						Portfolio Showcase
					</div>

					<!-- Heading -->
					<h1
						in:fly={{ x: -50, duration: 700, delay: 200 }}
						class="text-4xl font-extrabold tracking-tight text-gray-900 sm:text-5xl lg:text-6xl"
					>
						Howdy, Welcome to my
						<span class="text-orange-500"> Portfolio </span>
					</h1>

					<!-- Description -->
					<p in:fade={{ duration: 800, delay: 400 }} class="mt-6 text-lg leading-8 text-gray-600">
						Showcasing my journey from simple projects to complex applications. Explore my work,
						read about my experiences, and discover the projects I've built.
					</p>

					<!-- CTA Buttons -->
					<div class="mt-8 flex flex-wrap items-center gap-4">
						<button
							in:fly={{ y: 20, duration: 600, delay: 500 }}
							onclick={scrollToProjects}
							class="group relative overflow-hidden rounded-lg bg-orange-500 px-6 py-3 text-base font-semibold text-white transition-all hover:scale-105 hover:bg-orange-600"
						>
							<span class="relative z-10">View Projects</span>
							<div
								class="absolute inset-0 -z-0 bg-gradient-to-r from-orange-700 to-orange-600 opacity-0 transition-opacity group-hover:opacity-100"
							></div>
						</button>
						<a
							in:fly={{ y: 20, duration: 600, delay: 600 }}
							href="/blog"
							class="rounded-lg border border-gray-300 bg-white px-6 py-3 text-base font-semibold text-gray-900 shadow-sm transition-all hover:scale-105 hover:bg-gray-50 hover:shadow-md focus:ring-2 focus:ring-gray-400 focus:ring-offset-2 focus:outline-none"
						>
							Read Blog
						</a>
					</div>

					<!-- Stats -->
					<div
						in:fade={{ duration: 800, delay: 700 }}
						class="mt-12 grid grid-cols-2 gap-6 border-t border-gray-200 pt-8 lg:grid-cols-4"
					>
						<div class="flex flex-col items-center text-center">
							<div class="text-3xl font-bold text-orange-500 sm:text-4xl">✓</div>
							<div class="mt-1 text-sm font-medium text-gray-700">Projects</div>
							<div class="mt-1 text-xs text-gray-500">From simple to complex</div>
						</div>
						<div class="flex flex-col items-center text-center">
							<div class="text-3xl font-bold text-blue-500 sm:text-4xl">⚡</div>
							<div class="mt-1 text-sm font-medium text-gray-700">Modern Tech</div>
							<div class="mt-1 text-xs text-gray-500">Latest technologies</div>
						</div>
						<div class="flex flex-col items-center text-center">
							<div class="text-3xl font-bold text-green-500 sm:text-4xl">🔓</div>
							<div class="mt-1 text-sm font-medium text-gray-700">Open Source</div>
							<div class="mt-1 text-xs text-gray-500">Transparent code</div>
						</div>
						<div class="flex flex-col items-center text-center">
							<div class="text-3xl font-bold text-purple-500 sm:text-4xl">📚</div>
							<div class="mt-1 text-sm font-medium text-gray-700">Learning</div>
							<div class="mt-1 text-xs text-gray-500">Continuous growth</div>
						</div>
					</div>
				{/if}
			</div>

			<!-- Left Column - Image -->
			<div class="order-1 flex items-center justify-center lg:order-2">
				{#if mounted}
					<img
						in:fly={{ y: 30, duration: 1000, delay: 100 }}
						src={HeroImage}
						alt="Svelte Logo"
						class="w-full max-w-md lg:max-w-lg"
					/>
				{/if}
			</div>
		</div>
	</div>
</section>

<style>
</style>
