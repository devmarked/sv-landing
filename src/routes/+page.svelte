<script lang="ts">
	import { Hero, ProjectCard, WorkHistory } from '$lib';
	import type { Project } from '$lib';
	import FeedImage from '$lib/assets/feed.png';
	import OpoosImage from '$lib/assets/opoos.png';
	import TaskImage from '$lib/assets/task.png';
	import WeatherImage from '$lib/assets/weather.png';
	import ChatImage from '$lib/assets/chat.png';
	import VotingImage from '$lib/assets/voting.png';
	import BlogImage from '$lib/assets/blog.png';
	import DoodleImage from '$lib/assets/doodle.png';

	const demoProjects: Project[] = [
		{
			id: '1',
			title: 'FeedbackIQ',
			description:
				'FeedbackIQ is a comprehensive survey platform designed specifically for businesses to create, distribute, and analyze customer feedback with AI-powered insights.',
			technologies: [
				'Next.js',
				'TypeScript',
				'PostgreSQL',
				'Supabase',
				'TailwindCSS',
				'Shadcn UI',
				'Magic UI'
			],
		liveUrl: 'https://feedbackiq-smart.vercel.app/',
		githubUrl: 'https://github.com/devmarked/feedbackiq',
		imageUrl: FeedImage
		},
		{
			id: '2',
			title: 'Opoos',
			description:
				'Opoos is a comprehensive internal tool designed specifically for sales teams and project managers to streamline the proposal and quotation workflow for website development projects.',
			technologies: [
				'Next.js',
				'TypeScript',
				'Supabase',
				'TailwindCSS',
				'Shadcn UI',
				'Magic UI',
				'OpenAI',
				'n8n'
			],
		liveUrl: 'https://opoos.vercel.app/',
		githubUrl: 'https://github.com/devmarked/opoos',
		imageUrl: OpoosImage
		}
	];

	const svelteKitProjects: Project[] = [
		{
			id: 'svelte-1',
			title: 'Todo App',
			description:
				'A simple todo application with add, edit, delete, and filter functionality. Perfect for learning Svelte state management.',
		technologies: ['Svelte 5', 'TypeScript', 'Tailwind CSS'],
		liveUrl: 'https://sv-task.vercel.app/',
		githubUrl: 'https://github.com/devmarked/sv-task',
		imageUrl: TaskImage
		},
		{
			id: 'svelte-2',
			title: 'Weather Dashboard',
			description:
				'Real-time weather information with location search and forecasts. Shows Svelte reactivity in action.',
		technologies: ['Svelte 5', 'TypeScript', 'OpenWeather API', 'Tailwind CSS'],
		liveUrl: 'https://sv-weather-five.vercel.app/',
		githubUrl: 'https://github.com/devmarked/sv-weather',
		imageUrl: WeatherImage
		},
		{
			id: 'svelte-3',
			title: 'Chat',
			description:
				'Real-time chat application with rooms and message history. Demonstrates WebSocket integration.',
		technologies: ['Svelte 5', 'TypeScript', 'Tailwind CSS'],
		liveUrl: 'https://sv-chat.vercel.app/',
		githubUrl: 'https://github.com/devmarked/sv-chat',
		imageUrl: ChatImage
		},
		{
			id: 'svelte-4',
			title: 'Voting',
			description:
				'Interactive voting system with real-time updates. Shows advanced SvelteKit patterns.',
		technologies: ['SvelteKit', 'WebSockets', 'TypeScript', 'Tailwind CSS'],
		liveUrl: 'https://sv-voting.vercel.app/',
		githubUrl: 'https://github.com/devmarked/sv-voting',
		imageUrl: VotingImage
		},
		{
			id: 'svelte-5',
			title: 'Blog',
			description:
				'Simple blog application with markdown support and post management. Clean Svelte implementation.',
		technologies: ['Svelte 5', 'TypeScript', 'Tailwind CSS'],
		liveUrl: 'https://sv-md-blog.vercel.app/',
		githubUrl: 'https://github.com/devmarked/sv-md-blog',
		imageUrl: BlogImage
		},
		{
			id: 'svelte-6',
			title: 'DoodleMation',
			description:
				'Transform static images into dynamic animated videos using AI-powered generation.',
			technologies: [
				'Svelte 5',
				'TypeScript',
				'Tailwind CSS',
				'OpenAI',
				'Hailou API',
				'Supabase',
				'Vercel'
			],
		liveUrl: 'https://doodlemation.vercel.app/',
		githubUrl: 'https://github.com/devmarked/doodlemation',
		imageUrl: DoodleImage
		}
	];
</script>

<svelte:head>
	<title>Home - MarkCarlo</title>
</svelte:head>

<Hero />
<section id="work-history">
	<WorkHistory />
</section>

<!-- Demo Projects Section -->
<section id="demo-projects" class="bg-white py-16 sm:py-24">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<!-- Section Header -->
		<div class="mx-auto max-w-2xl text-center">
			<h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Demo Projects</h2>
			<p class="mt-4 text-lg text-gray-600">
				A collection of demo projects built with Next.js showcasing a range of web development
				concepts, from simple UI components to more complex full-stack applications.
			</p>
		</div>

		<!-- Projects Grid -->
		<div class="mt-16 grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
			{#each demoProjects as project (project.id)}
				<ProjectCard
					title={project.title}
					description={project.description}
					technologies={project.technologies}
					liveUrl={project.liveUrl}
					githubUrl={project.githubUrl}
					imageUrl={project.imageUrl}
				/>
			{/each}
		</div>
	</div>
</section>

<!-- SvelteKit Demo Projects Section -->
<section id="svelte-projects" class="bg-gray-50 py-16 sm:py-24">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<!-- Section Header -->
		<div class="mx-auto max-w-2xl text-center">
			<h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
				Svelte Demo Projects
			</h2>
			<p class="mt-4 text-lg text-gray-600">
				Hands-on Svelte and SvelteKit projects demonstrating core concepts, from basic components to
				advanced real-time applications.
			</p>
		</div>

		<!-- Projects Grid -->
		<div class="mt-16 grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
			{#each svelteKitProjects as project (project.id)}
				<ProjectCard
					title={project.title}
					description={project.description}
					technologies={project.technologies}
					liveUrl={project.liveUrl}
					githubUrl={project.githubUrl}
					imageUrl={project.imageUrl}
				/>
			{/each}
		</div>
	</div>
</section>
