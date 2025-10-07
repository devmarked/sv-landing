<script lang="ts">
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import image1 from '$lib/assets/1.png';
	import image2 from '$lib/assets/2.png';
	import image3 from '$lib/assets/3.png';
	import image4 from '$lib/assets/4.png';
	import image5 from '$lib/assets/5.png';

	interface WorkExperience {
		id: string;
		title: string;
		company: string;
		location: string;
		period: string;
		description: string;
		responsibilities: string[];
		technologies?: string[];
		image?: string;
	}

	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});

	const experiences: WorkExperience[] = [
		{
			id: '1',
			title: 'Web Developer Intern',
			company: 'Central Mindanao University',
			location: 'Bukidnon, Philippines',
			period: 'Internship',
			description:
				'Web developer internship focused on PHP programming, CodeIgniter, Laravel, and WordPress development.',
			responsibilities: [
				'Developed web application for journal of science publications',
				'Worked with PHP programming and modern PHP frameworks',
				'Implemented features using CodeIgniter and Laravel frameworks',
				'Created and maintained WordPress websites and plugins',
				'Collaborated with development team on university web projects'
			],
			technologies: ['PHP', 'CodeIgniter', 'Laravel', 'WordPress', 'Web Development'],
			image: image1
		},
		{
			id: '2',
			title: 'Web Project Manager',
			company: 'Syntactics Inc.',
			location: 'Cagayan De Oro City, Philippines',
			period: 'September 2018 - October 2021',
			description:
				'Managed cross-functional development teams and coordinated project delivery across multiple stakeholders and departments.',
			responsibilities: [
				'Led cross-functional teams of developers, designers, and QA specialists, fostering collaboration and clear communication across internal departments and external stakeholders to ensure smooth project execution',
				'Developed and maintained detailed project plans with work breakdown structures, resource allocation, and timelines while facilitating regular meetings and advocating for process improvements'
			],
			technologies: [
				'Project Management',
				'Team Leadership',
				'Agile',
				'Communication',
				'Process Improvement'
			],
			image: image2
		},
		{
			id: '3',
			title: 'Web Developer',
			company: 'Communiqu',
			location: 'Remote',
			period: 'November 2021 - January 2023',
			description:
				"Spearheaded the development and maintenance of the company's WordPress website, enhancing performance, scalability, and user experience through custom front-end framework integration.",
			responsibilities: [
				'Developed and maintained the company website using WordPress with custom front-end framework integration, delivering faster load times, improved scalability, and seamless user experience',
				'Collaborated with designers and marketing teams to align web features with campaign goals, implemented SEO best practices, and optimized website performance and security protocols'
			],
			technologies: [
				'WordPress',
				'Custom Front-end Framework',
				'SEO',
				'Performance Optimization',
				'Security'
			],
			image: image3
		},
		{
			id: '4',
			title: 'Web3 Developer',
			company: 'Self-Employed / Freelancer',
			location: 'Remote',
			period: 'January 2023 - July 2025',
			description:
				'Built tools and automation solutions using modern Web3 technologies, focusing on blockchain integration, DeFi protocols, and scalable developer tools.',
			responsibilities: [
				'Built tools using Next.js, Supabase, and blockchain APIs, delivering scalable, user-centric platforms while developing automation workflows with Playwright for wallet creation, transaction simulation, and performance benchmarking',
				'Designed and deployed automation scripts for wallet management and conducted comprehensive testing and audits of blockchain protocols and DeFi applications, identifying vulnerabilities and implementing security fixes while documenting processes for enhanced developer productivity'
			],
			technologies: ['Next.js', 'Supabase', 'Blockchain APIs', 'Playwright', 'DeFi', 'Web3'],
			image: image4
		},
		{
			id: '5',
			title: 'Fullstack Developer',
			company: 'Self-Employed / Freelancer',
			location: 'Remote',
			period: 'July 2025 - Present',
			description:
				'Developed and launched SaaS applications leveraging AI and Web3 technologies, focusing on productivity, automation, and robust system architecture.',
			responsibilities: [
				'Built and launched SaaS applications leveraging AI technologies, with a focus on productivity tools, automation platforms, and Web3 integrations, while designing and implementing end-to-end system architecture',
				'Implemented user authentication, role-based access control, relational and vector database schemas, scalable cloud deployment workflows, and documented development best practices for knowledge sharing'
			],
			technologies: ['AI', 'SaaS', 'Web3', 'Authentication', 'Database Design', 'Cloud Deployment'],
			image: image5
		}
	];
</script>

<!-- Work History Section -->
<section id="work-history" class="bg-gradient-to-b from-gray-50 to-white py-16 sm:py-24">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<!-- Section Header -->
		<div class="mx-auto max-w-2xl text-center">
			<h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Work History</h2>
			<p class="mt-4 text-lg text-gray-600">
				My professional journey and experience building great products
			</p>
		</div>

		<!-- Timeline -->
		<div class="relative mt-16">
			{#if mounted}
				<!-- Vertical Line -->
				<div
					class="absolute top-0 bottom-0 left-8 w-0.5 bg-gradient-to-b from-orange-500 via-orange-400 to-orange-300 md:left-1/2 md:-translate-x-1/2"
				></div>

				<!-- Timeline Items -->
				<div class="space-y-12">
					{#each experiences as exp, index (exp.id)}
						<div
							in:fly={{ y: 30, duration: 600, delay: 200 + index * 100 }}
							class="relative grid md:grid-cols-2 md:gap-8"
						>
							<!-- Timeline Dot -->
							<div
								class="absolute left-8 flex h-6 w-6 -translate-x-1/2 items-center justify-center md:left-1/2"
							>
								<div
									class="h-6 w-6 rounded-full border-4 border-white bg-orange-500 shadow-lg ring-4 ring-orange-100"
								></div>
							</div>

							<!-- Content - alternates left/right on desktop -->
							<div
								class="md:col-span-1 {index % 2 === 0
									? 'md:pr-12 md:text-right'
									: 'md:col-start-2 md:pl-12'} ml-20 md:ml-0"
							>
								<!-- Card -->
								<div
									class="group rounded-xl border border-gray-100 bg-white p-6 shadow-md transition-all hover:shadow-xl"
								>
									<!-- Image -->
									{#if exp.image}
										<div class="mb-4 flex justify-center">
											<img src={exp.image} alt={exp.company} class="h-auto w-[300px] rounded-md" />
										</div>
									{/if}

									<!-- Period Badge -->
									<div
										class="text-md mb-3 inline-flex items-center gap-2 rounded-full bg-orange-50 px-3 py-1 font-medium text-orange-700"
									>
										<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
											<path
												stroke-linecap="round"
												stroke-linejoin="round"
												stroke-width="2"
												d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
											/>
										</svg>
										{exp.period}
									</div>

									<!-- Title & Company -->
									<h3
										class="text-xl font-bold text-gray-900 transition-colors group-hover:text-orange-600"
									>
										{exp.title}
									</h3>
									<div class="mt-1 flex items-center gap-2 text-gray-600">
										<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
											<path
												stroke-linecap="round"
												stroke-linejoin="round"
												stroke-width="2"
												d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"
											/>
										</svg>
										<span class="font-medium">{exp.company}</span>
										<span class="text-gray-400">•</span>
										<span class="text-md">{exp.location}</span>
									</div>

									<!-- Description -->
									<p class="mt-3 text-left leading-relaxed text-gray-600">
										{exp.description}
									</p>

									<!-- Responsibilities -->
									<ul class="mt-4 space-y-2 text-left">
										{#each exp.responsibilities as responsibility}
											<li class="text-md flex items-start gap-2 text-gray-600">
												<span class="mt-1 flex-shrink-0 text-orange-500">▸</span>
												<span>{responsibility}</span>
											</li>
										{/each}
									</ul>

									<!-- Technologies -->
									{#if exp.technologies}
										<div class="mt-4 flex flex-wrap gap-2">
											{#each exp.technologies as tech}
												<span
													class="rounded-md bg-gray-100 px-2.5 py-1 text-xs font-medium text-gray-700"
												>
													{tech}
												</span>
											{/each}
										</div>
									{/if}
								</div>
							</div>
						</div>
					{/each}
				</div>
			{/if}
		</div>
	</div>
</section>
