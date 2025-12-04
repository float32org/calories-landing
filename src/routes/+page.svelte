<script lang="ts">
	import { resolve } from '$app/paths';
	import { PUBLIC_APP_URL } from '$env/static/public';
	import { Button } from '$lib/components/ui/button';
	import {
		ArrowRight,
		Camera,
		Check,
		ChevronLeft,
		ChevronRight,
		Droplets,
		Ellipsis,
		Goal,
		Hamburger,
		LayoutDashboard,
		Refrigerator,
		Scale,
		Sparkles
	} from '@lucide/svelte';
	import Moon from '@lucide/svelte/icons/moon';
	import Sun from '@lucide/svelte/icons/sun';
	import { toggleMode } from 'mode-watcher';

	const features = [
		'Unlimited AI meal analysis',
		'Photo-based calorie tracking',
		'Personal AI nutrition assistant',
		'Weight tracking & goals',
		'Preference learning',
		'7-day free trial'
	];
</script>

<svelte:head>
	<title>Calories - Track your nutrition, simply.</title>
	<meta
		name="description"
		content="Track your nutrition simply with AI-powered meal logging, calorie tracking, and personalized insights. Snap a photo or describe your meal to get instant nutritional estimates."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Calories - Track your nutrition, simply." />
	<meta
		property="og:description"
		content="Track your nutrition simply with AI-powered meal logging, calorie tracking, and personalized insights."
	/>
	<meta property="og:url" content="https://burncalories.app" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content="Calories - Track your nutrition, simply." />
	<meta
		name="twitter:description"
		content="Track your nutrition simply with AI-powered meal logging, calorie tracking, and personalized insights."
	/>
</svelte:head>

<div class="flex min-h-screen flex-col">
	<header class="py-4">
		<div class="container mx-auto flex items-center justify-between px-4 md:px-6">
			<div class="flex items-center gap-2 font-medium text-xl">
				<div
					class="size-8 rounded-lg bg-primary flex items-center justify-center text-primary-foreground"
				>
					<Hamburger class="size-5" />
				</div>
				Calories
			</div>
			<nav class="hidden md:flex items-center gap-6 text-sm font-medium text-muted-foreground">
				<a href="#features" class="hover:text-foreground transition-colors">Features</a>
				<a href="#pricing" class="hover:text-foreground transition-colors">Pricing</a>
				<a
					href="https://github.com/joeychilson/calories"
					target="_blank"
					rel="noopener noreferrer"
					class="hover:text-foreground transition-colors">GitHub</a
				>
			</nav>
			<div class="flex items-center gap-2">
				<Button onclick={toggleMode} variant="outline" size="icon" class="size-9">
					<Sun class="size-4 rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
					<Moon
						class="absolute size-4 rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
					/>
					<span class="sr-only">Toggle theme</span>
				</Button>
				<Button size="sm" href="{PUBLIC_APP_URL}/signin">Sign In</Button>
			</div>
		</div>
	</header>

	<main class="flex-1">
		<section class="relative pt-8 pb-40 md:pt-12 md:pb-52 overflow-hidden">
			<div class="container px-4 md:px-6 mx-auto">
				<div class="flex flex-col items-center text-center gap-6 max-w-3xl mx-auto mb-12">
					<h1 class="text-4xl md:text-6xl font-bold tracking-tight text-balance">
						Track your nutrition, <span class="text-primary">simply.</span>
					</h1>
					<p class="text-lg text-muted-foreground text-balance max-w-xl">
						Log meals, track water, and reach your weight goals with AI-powered insights.
					</p>
					<div class="flex flex-col sm:flex-row gap-4 w-full sm:w-auto">
						<Button size="lg" class="gap-2" href="{PUBLIC_APP_URL}/signin">
							Start Free Trial <ArrowRight class="size-4" />
						</Button>
					</div>
				</div>

				<div class="relative mx-auto max-w-md perspective-1000">
					<div
						class="relative rounded-xl border bg-background shadow-2xl overflow-hidden transform rotate-x-12 transition-transform duration-500 hover:rotate-0"
					>
						<div class="h-14 bg-background flex items-center justify-between px-4">
							<div class="flex items-center gap-2 font-medium">
								<div
									class="bg-primary text-primary-foreground flex size-6 items-center justify-center rounded-md"
								>
									<Hamburger class="size-4" />
								</div>
								Calories
							</div>
							<div class="flex items-center gap-1">
								<div class="size-8 rounded-md border flex items-center justify-center">
									<Sparkles class="size-4 text-muted-foreground" />
								</div>
								<div class="size-8 rounded-md border flex items-center justify-center">
									<Refrigerator class="size-4 text-muted-foreground" />
								</div>
								<div class="size-8 rounded-md border flex items-center justify-center">
									<Goal class="size-4 text-muted-foreground" />
								</div>
								<div
									class="size-8 rounded-md bg-primary text-primary-foreground flex items-center justify-center text-xs font-medium"
								>
									J
								</div>
							</div>
						</div>
						<div class="p-4 space-y-3 bg-background">
							<div class="flex items-center justify-between px-2">
								<ChevronLeft class="size-5 text-muted-foreground" />
								<div class="text-center">
									<div class="text-xs text-muted-foreground">2025</div>
									<div class="font-bold">Today</div>
								</div>
								<ChevronRight class="size-5 text-muted-foreground" />
							</div>
							<div class="flex flex-col items-center justify-center py-2">
								<div class="relative" style="width: 200px; height: 200px;">
									<svg width="200" height="200" viewBox="0 0 200 200">
										<circle
											cx="100"
											cy="100"
											r="84"
											fill="none"
											stroke="var(--muted)"
											stroke-width="16"
											stroke-linecap="round"
										/>
										<path
											d="M 100 16 A 84 84 0 0 1 184 100"
											fill="none"
											stroke="var(--chart-1)"
											stroke-width="16"
											stroke-linecap="round"
										/>
									</svg>
									<div
										class="absolute inset-0 flex flex-col items-center justify-center text-center"
									>
										<span class="text-sm font-medium text-muted-foreground">Remaining</span>
										<span class="text-4xl font-bold tracking-tighter text-foreground">1708</span>
										<span class="text-xs font-medium text-muted-foreground mt-1">kcal</span>
									</div>
								</div>
								<div class="mt-2 flex items-center gap-6">
									<div class="flex flex-col items-center gap-1">
										<span class="text-sm font-bold text-blue-500 dark:text-blue-400">
											24<span class="text-muted-foreground/60 font-medium">/182g</span>
										</span>
										<div class="h-1.5 w-16 overflow-hidden rounded-full bg-muted">
											<div
												class="h-full rounded-full bg-blue-500 dark:bg-blue-400"
												style="width: 13%"
											></div>
										</div>
										<span
											class="text-[10px] font-bold uppercase tracking-wider text-muted-foreground/60"
											>Protein</span
										>
									</div>
									<div class="flex flex-col items-center gap-1">
										<span class="text-sm font-bold text-amber-500 dark:text-amber-400">
											72<span class="text-muted-foreground/60 font-medium">/212g</span>
										</span>
										<div class="h-1.5 w-16 overflow-hidden rounded-full bg-muted">
											<div
												class="h-full rounded-full bg-amber-500 dark:bg-amber-400"
												style="width: 34%"
											></div>
										</div>
										<span
											class="text-[10px] font-bold uppercase tracking-wider text-muted-foreground/60"
											>Carbs</span
										>
									</div>
									<div class="flex flex-col items-center gap-1">
										<span class="text-sm font-bold text-rose-500 dark:text-rose-400">
											36<span class="text-muted-foreground/60 font-medium">/94g</span>
										</span>
										<div class="h-1.5 w-16 overflow-hidden rounded-full bg-muted">
											<div
												class="h-full rounded-full bg-rose-500 dark:bg-rose-400"
												style="width: 38%"
											></div>
										</div>
										<span
											class="text-[10px] font-bold uppercase tracking-wider text-muted-foreground/60"
											>Fat</span
										>
									</div>
								</div>
							</div>
							<div class="flex shrink-0 items-center gap-3 rounded-xl bg-muted/30 p-3">
								<div class="relative size-12 shrink-0">
									<svg class="size-full -rotate-90" viewBox="0 0 40 40">
										<circle
											cx="20"
											cy="20"
											r="16"
											fill="none"
											class="stroke-muted"
											stroke-width="3"
										/>
									</svg>
									<Scale class="absolute inset-0 m-auto size-5 text-muted-foreground" />
								</div>
								<div class="min-w-0 flex-1">
									<div class="flex items-baseline gap-1">
										<span class="text-lg font-bold tabular-nums">200</span>
										<span class="text-xs text-muted-foreground">/ 180 lbs</span>
									</div>
									<span
										class="text-[10px] font-medium uppercase tracking-wider text-muted-foreground"
									>
										Not logged · 20.0 lbs to go
									</span>
								</div>
							</div>
							<div class="flex shrink-0 items-center gap-3 rounded-xl bg-muted/30 p-3">
								<div class="relative size-12 shrink-0">
									<svg class="size-full -rotate-90" viewBox="0 0 40 40">
										<circle
											cx="20"
											cy="20"
											r="16"
											fill="none"
											class="stroke-muted"
											stroke-width="3"
										/>
										<circle
											cx="20"
											cy="20"
											r="16"
											fill="none"
											class="stroke-blue-500"
											stroke-width="3"
											stroke-linecap="round"
											stroke-dasharray="100.53"
											stroke-dashoffset="20"
										/>
									</svg>
									<Droplets class="absolute inset-0 m-auto size-5 text-blue-500" />
								</div>
								<div class="min-w-0 flex-1">
									<div class="flex items-baseline gap-1">
										<span class="text-lg font-bold tabular-nums">80</span>
										<span class="text-xs text-muted-foreground">/ 100oz</span>
									</div>
									<span
										class="text-[10px] font-medium uppercase tracking-wider text-muted-foreground"
									>
										Water intake
									</span>
								</div>
								<div class="flex gap-1">
									<Button
										size="sm"
										variant="ghost"
										class="size-8 rounded-lg px-0 text-xs font-semibold text-muted-foreground"
										>−</Button
									>
									<Button
										size="sm"
										variant="outline"
										class="h-8 rounded-lg px-2 text-xs font-semibold">+8</Button
									>
									<Button
										size="sm"
										variant="outline"
										class="h-8 rounded-lg px-2 text-xs font-semibold">+16</Button
									>
								</div>
							</div>
							<div class="pt-1">
								<div class="flex items-center justify-between mb-3">
									<div class="flex items-center gap-2">
										<span class="font-bold">Meals</span>
										<span class="text-xs bg-muted px-1.5 py-0.5 rounded">1</span>
									</div>
									<Button size="sm" class="h-8 rounded-lg font-semibold">+ Log Meal</Button>
								</div>
								<div class="group relative overflow-hidden rounded-2xl bg-muted/30">
									<div class="flex items-stretch">
										<div
											class="w-1 shrink-0 rounded-l-2xl"
											style="background-color: var(--chart-1)"
										></div>
										<div class="flex min-w-0 flex-1 flex-col justify-center p-2 pl-3">
											<div class="flex items-start justify-between gap-2">
												<div class="min-w-0 flex-1">
													<h3 class="line-clamp-1 font-bold leading-snug text-foreground">
														3 Tacos
													</h3>
													<p class="text-[11px] text-muted-foreground">12:40 PM</p>
												</div>
												<Ellipsis class="size-4 shrink-0 text-muted-foreground" />
											</div>
											<div class="flex items-center justify-between">
												<div class="flex items-center gap-1">
													<span
														class="rounded-md bg-blue-500/10 px-1.5 py-0.5 text-[10px] font-semibold text-blue-500 dark:bg-blue-400/10 dark:text-blue-400"
														>24g P</span
													>
													<span
														class="rounded-md bg-amber-500/10 px-1.5 py-0.5 text-[10px] font-semibold text-amber-500 dark:bg-amber-400/10 dark:text-amber-400"
														>72g C</span
													>
													<span
														class="rounded-md bg-rose-500/10 px-1.5 py-0.5 text-[10px] font-semibold text-rose-500 dark:bg-rose-400/10 dark:text-rose-400"
														>36g F</span
													>
												</div>
												<div
													class="flex items-baseline gap-0.5 rounded-lg bg-foreground/5 px-2 py-1"
												>
													<span class="text-base font-bold tabular-nums leading-none">720</span>
													<span
														class="text-[9px] font-bold uppercase tracking-wide text-muted-foreground"
														>kcal</span
													>
												</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div
						class="absolute -z-10 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[120%] h-[120%] bg-primary/5 blur-3xl rounded-full pointer-events-none"
					></div>
				</div>
			</div>
		</section>

		<section id="features" class="py-20">
			<div class="container px-4 md:px-6 mx-auto">
				<div class="text-center max-w-2xl mx-auto mb-16">
					<h2 class="text-3xl font-bold tracking-tight sm:text-4xl mb-4">
						Everything you need to stay on track
					</h2>
					<p class="text-muted-foreground text-lg">
						Simple, powerful tools to help you reach your goals.
					</p>
				</div>

				<div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
					<div class="rounded-2xl bg-muted/40 p-6">
						<div
							class="size-12 rounded-lg bg-orange-100 dark:bg-orange-900/20 text-orange-600 dark:text-orange-400 flex items-center justify-center mb-4"
						>
							<Camera class="size-6" />
						</div>
						<h3 class="text-lg font-bold mb-3">AI Meal Logging</h3>
						<ul class="space-y-2 text-sm text-muted-foreground">
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Snap a photo or
								describe your meal
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>AI estimates
								calories and macros instantly
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Manual entry option
								too
							</li>
						</ul>
					</div>

					<div class="rounded-2xl bg-muted/40 p-6">
						<div
							class="size-12 rounded-lg bg-blue-100 dark:bg-blue-900/20 text-blue-600 dark:text-blue-400 flex items-center justify-center mb-4"
						>
							<LayoutDashboard class="size-6" />
						</div>
						<h3 class="text-lg font-bold mb-3">Smart Dashboard</h3>
						<ul class="space-y-2 text-sm text-muted-foreground">
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Track calories,
								protein, carbs, and fat
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Visual progress
								rings and bars
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Date navigation to
								review history
							</li>
						</ul>
					</div>

					<div class="rounded-2xl bg-muted/40 p-6">
						<div
							class="size-12 rounded-lg bg-purple-100 dark:bg-purple-900/20 text-purple-600 dark:text-purple-400 flex items-center justify-center mb-4"
						>
							<Sparkles class="size-6" />
						</div>
						<h3 class="text-lg font-bold mb-3">AI Food Assistant</h3>
						<ul class="space-y-2 text-sm text-muted-foreground">
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Get personalized
								meal suggestions
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Ask nutrition
								questions
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Learns your
								preferences over time
							</li>
						</ul>
					</div>

					<div class="rounded-2xl bg-muted/40 p-6">
						<div
							class="size-12 rounded-lg bg-green-100 dark:bg-green-900/20 text-green-600 dark:text-green-400 flex items-center justify-center mb-4"
						>
							<Scale class="size-6" />
						</div>
						<h3 class="text-lg font-bold mb-3">Weight & Water Tracking</h3>
						<ul class="space-y-2 text-sm text-muted-foreground">
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Set and track weight
								goals
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Quick-add water
								buttons
							</li>
							<li class="flex items-center gap-2">
								<span class="size-1 rounded-full bg-muted-foreground/50"></span>Imperial or metric
								units
							</li>
						</ul>
					</div>
				</div>
			</div>
		</section>

		<section id="pricing" class="py-20">
			<div class="container px-4 md:px-6 mx-auto">
				<div class="text-center max-w-2xl mx-auto mb-12">
					<h2 class="text-3xl font-bold tracking-tight sm:text-4xl mb-4">Simple pricing</h2>
					<p class="text-muted-foreground text-lg">
						Start with a 7-day free trial. Cancel anytime.
					</p>
				</div>

				<div class="max-w-sm mx-auto">
					<div
						class="flex flex-col gap-6 rounded-3xl border border-border/50 bg-card/50 p-6 shadow-sm sm:p-8"
					>
						<div class="mb-2 space-y-1 text-center">
							<h3 class="text-lg font-bold">Calories Pro</h3>
							<div class="flex items-baseline justify-center gap-1">
								<span class="text-4xl font-bold">$3</span>
								<span class="text-muted-foreground">/month</span>
							</div>
							<p class="text-xs text-muted-foreground">7-day free trial. Cancel anytime.</p>
						</div>
						<div class="space-y-3">
							{#each features as feature (feature)}
								<div class="flex items-center gap-3">
									<div class="flex size-5 items-center justify-center rounded-full bg-primary/10">
										<Check class="size-3 text-primary" />
									</div>
									<span class="text-sm">{feature}</span>
								</div>
							{/each}
						</div>
						<Button class="h-12 w-full rounded-xl font-bold" href="{PUBLIC_APP_URL}/signin"
							>Start Free Trial</Button
						>
						<p class="text-center text-[10px] text-muted-foreground/70">
							Secure payment via Stripe. Cancel anytime before trial ends.
						</p>
					</div>
					<p class="text-center text-xs text-muted-foreground/60 mt-6">
						Prefer to self-host?
						<a
							href="https://github.com/joeychilson/calories"
							target="_blank"
							rel="noopener noreferrer"
							class="underline hover:text-muted-foreground"
						>
							View on GitHub
						</a>
					</p>
				</div>
			</div>
		</section>
	</main>

	<footer class="py-8">
		<div class="container px-4 md:px-6 mx-auto">
			<div class="flex flex-col md:flex-row items-center justify-between gap-4">
				<div class="flex items-center gap-2 font-medium">
					<div
						class="size-8 rounded-lg bg-primary flex items-center justify-center text-primary-foreground"
					>
						<Hamburger class="size-5" />
					</div>
					Calories
				</div>
				<nav class="flex items-center gap-6 text-sm text-muted-foreground">
					<a href="#features" class="hover:text-foreground transition-colors">Features</a>
					<a href="#pricing" class="hover:text-foreground transition-colors">Pricing</a>
					<a
						href="https://github.com/joeychilson/calories"
						target="_blank"
						rel="noopener noreferrer"
						class="hover:text-foreground transition-colors">GitHub</a
					>
					<a href={resolve('/privacy')} class="hover:text-foreground transition-colors">Privacy</a>
					<a href={resolve('/terms')} class="hover:text-foreground transition-colors">Terms</a>
				</nav>
				<p class="text-sm text-muted-foreground">
					&copy; {new Date().getFullYear()} Calories
				</p>
			</div>
		</div>
	</footer>
</div>

<style>
	.perspective-1000 {
		perspective: 1000px;
	}
</style>
