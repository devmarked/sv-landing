<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
	import { Header, Footer } from '$lib';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<meta name="description" content="My Svelte learning journey - from simple to complex projects" />
</svelte:head>

<div class="flex min-h-screen flex-col">
	<Header />
	
	<main class="flex-1">
		{@render children?.()}
	</main>
	
	<Footer />
</div>
