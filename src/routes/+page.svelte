<script lang="ts">
	import { resolve } from '$app/paths';
	import { PUBLIC_APP_URL } from '$env/static/public';
	import { Button } from '$lib/components/ui/button';
	import {
		ArrowRight,
		Camera,
		ChartNoAxesCombined,
		Check,
		ChefHat,
		ChevronLeft,
		ChevronRight,
		CookingPot,
		Droplets,
		Ellipsis,
		Hamburger,
		LayoutDashboard,
		Scale,
		Sparkles,
		TrendingDown
	} from '@lucide/svelte';
	import Moon from '@lucide/svelte/icons/moon';
	import Sun from '@lucide/svelte/icons/sun';
	import { toggleMode } from 'mode-watcher';

	const features = [
		'Log meals by photo or text',
		'Personal food assistant',
		'Calorie & macro tracking',
		'Weight & water tracking',
		'Pantry & shopping lists',
		'Progress charts & streaks',
		'7-day free trial'
	];
</script>

<svelte:head>
	<title>Calories - Track your food and nutrition, simply.</title>
	<meta
		name="description"
		content="The simple way to track what you eat. Log meals with a photo or a sentence. Track calories, macros, weight, water, and progress—all in one place."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Calories - Track your food and nutrition, simply." />
	<meta
		property="og:description"
		content="Log meals with a photo or a sentence. Track calories, macros, weight, water, and progress—all in one place."
	/>
	<meta property="og:url" content="https://burncalories.app" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content="Calories - Track your food and nutrition, simply." />
	<meta
		name="twitter:description"
		content="Log meals with a photo or a sentence. Track calories, macros, weight, water, and progress—all in one place."
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
					href="https://github.com/float32org/calories"
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
						Track your food and nutrition, <span class="text-primary">simply.</span>
					</h1>
					<p class="text-lg text-muted-foreground text-balance max-w-xl">
						Log meals with a snap or a sentence. Track weight, water, and progress—all in one place.
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
								<Button variant="outline" size="icon-sm">
									<ChefHat class="size-4 text-muted-foreground" />
								</Button>
								<Button variant="outline" size="icon-sm">
									<CookingPot class="size-4 text-muted-foreground" />
								</Button>
								<Button variant="outline" size="icon-sm">
									<ChartNoAxesCombined class="size-4 text-muted-foreground" />
								</Button>
								<div
									class="size-8 rounded-md bg-primary text-primary-foreground flex items-center justify-center text-xs font-medium"
								>
									J
								</div>
							</div>
						</div>
						<div class="p-4 space-y-3 bg-background">
							<div class="flex items-center justify-between">
								<div class="size-9 flex items-center justify-center rounded-md hover:bg-muted">
									<ChevronLeft class="size-4 text-muted-foreground" />
								</div>
								<div class="text-center">
									<div class="text-xs text-muted-foreground">2025</div>
									<div class="font-bold">Today</div>
								</div>
								<div class="size-9 flex items-center justify-center rounded-md hover:bg-muted">
									<ChevronRight class="size-4 text-muted-foreground" />
								</div>
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
										<span class="text-sm font-bold" style="color: oklch(0.65 0.12 250)">
											24<span class="text-muted-foreground/60 font-medium">/182g</span>
										</span>
										<div class="h-1.5 w-16 overflow-hidden rounded-full bg-muted">
											<div
												class="h-full rounded-full"
												style="width: 13%; background: oklch(0.65 0.12 250)"
											></div>
										</div>
										<span
											class="text-[10px] font-bold uppercase tracking-wider text-muted-foreground/60"
											>Protein</span
										>
									</div>
									<div class="flex flex-col items-center gap-1">
										<span class="text-sm font-bold" style="color: oklch(0.75 0.14 70)">
											72<span class="text-muted-foreground/60 font-medium">/212g</span>
										</span>
										<div class="h-1.5 w-16 overflow-hidden rounded-full bg-muted">
											<div
												class="h-full rounded-full"
												style="width: 34%; background: oklch(0.75 0.14 70)"
											></div>
										</div>
										<span
											class="text-[10px] font-bold uppercase tracking-wider text-muted-foreground/60"
											>Carbs</span
										>
									</div>
									<div class="flex flex-col items-center gap-1">
										<span class="text-sm font-bold" style="color: oklch(0.65 0.16 15)">
											36<span class="text-muted-foreground/60 font-medium">/94g</span>
										</span>
										<div class="h-1.5 w-16 overflow-hidden rounded-full bg-muted">
											<div
												class="h-full rounded-full"
												style="width: 38%; background: oklch(0.65 0.16 15)"
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
										<circle
											cx="20"
											cy="20"
											r="16"
											fill="none"
											class="stroke-primary"
											stroke-width="3"
											stroke-linecap="round"
											stroke-dasharray="100.53"
											stroke-dashoffset="85"
										/>
									</svg>
									<Scale class="absolute inset-0 m-auto size-5 text-muted-foreground" />
								</div>
								<div class="min-w-0 flex-1">
									<div class="flex items-baseline gap-1">
										<span class="text-lg font-bold tabular-nums">197</span>
										<span class="text-xs text-muted-foreground">/ 180 lbs</span>
									</div>
									<span
										class="text-[10px] font-medium uppercase tracking-wider text-muted-foreground"
									>
										Logged · 17.0 lbs to go
									</span>
								</div>
								<div
									class="flex items-center gap-1 rounded-lg bg-emerald-500/10 px-2 py-1 text-xs font-bold text-emerald-500"
								>
									<TrendingDown class="size-3" />
									-3.0
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
											class="stroke-secondary"
											stroke-width="3"
											stroke-linecap="round"
											stroke-dasharray="100.53"
											stroke-dashoffset="20"
										/>
									</svg>
									<Droplets class="absolute inset-0 m-auto size-5 text-secondary" />
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
										<span
											class="text-xs bg-muted px-2 py-1 rounded-full font-medium text-muted-foreground"
											>1</span
										>
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
														class="rounded-md px-1.5 py-0.5 text-[10px] font-semibold"
														style="background: oklch(0.65 0.12 250 / 0.15); color: oklch(0.65 0.12 250)"
														>24g P</span
													>
													<span
														class="rounded-md px-1.5 py-0.5 text-[10px] font-semibold"
														style="background: oklch(0.75 0.14 70 / 0.15); color: oklch(0.75 0.14 70)"
														>72g C</span
													>
													<span
														class="rounded-md px-1.5 py-0.5 text-[10px] font-semibold"
														style="background: oklch(0.65 0.16 15 / 0.15); color: oklch(0.65 0.16 15)"
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
						Everything you need, nothing you don't
					</h2>
					<p class="text-muted-foreground text-lg">
						Simple tools to help you eat better and feel good.
					</p>
				</div>

				<div class="grid md:grid-cols-2 gap-4 max-w-4xl mx-auto">
					<div class="rounded-2xl border border-border/50 bg-card/30 p-6">
						<div
							class="size-11 rounded-xl flex items-center justify-center mb-4"
							style="background: oklch(0.7 0.13 50 / 0.15); color: oklch(0.7 0.13 50)"
						>
							<Camera class="size-5" />
						</div>
						<h3 class="text-base font-bold mb-2">Easy Meal Logging</h3>
						<p class="text-sm text-muted-foreground leading-relaxed">
							Snap a photo or just describe what you ate. We estimate calories and macros for you.
						</p>
					</div>

					<div class="rounded-2xl border border-border/50 bg-card/30 p-6">
						<div
							class="size-11 rounded-xl flex items-center justify-center mb-4"
							style="background: oklch(0.75 0.12 85 / 0.15); color: oklch(0.75 0.12 85)"
						>
							<LayoutDashboard class="size-5" />
						</div>
						<h3 class="text-base font-bold mb-2">See Your Progress</h3>
						<p class="text-sm text-muted-foreground leading-relaxed">
							Visual rings show your daily calories and macros at a glance. Track streaks and see
							trends over time.
						</p>
					</div>

					<div class="rounded-2xl border border-border/50 bg-card/30 p-6">
						<div
							class="size-11 rounded-xl flex items-center justify-center mb-4"
							style="background: oklch(0.7 0.12 145 / 0.15); color: oklch(0.7 0.12 145)"
						>
							<Sparkles class="size-5" />
						</div>
						<h3 class="text-base font-bold mb-2">Personal Food Assistant</h3>
						<p class="text-sm text-muted-foreground leading-relaxed">
							Ask for meal ideas, get suggestions based on what's in your kitchen, and save recipes.
							It learns what you like.
						</p>
					</div>

					<div class="rounded-2xl border border-border/50 bg-card/30 p-6">
						<div
							class="size-11 rounded-xl flex items-center justify-center mb-4"
							style="background: oklch(0.65 0.10 195 / 0.15); color: oklch(0.65 0.10 195)"
						>
							<Scale class="size-5" />
						</div>
						<h3 class="text-base font-bold mb-2">Weight & Water</h3>
						<p class="text-sm text-muted-foreground leading-relaxed">
							Set a weight goal and track your progress. Log water with quick-tap buttons to stay
							hydrated.
						</p>
					</div>
				</div>
			</div>
		</section>

		<section id="pricing" class="py-20">
			<div class="container px-4 md:px-6 mx-auto">
				<div class="text-center max-w-2xl mx-auto mb-12">
					<h2 class="text-3xl font-bold tracking-tight sm:text-4xl mb-4">Simple pricing</h2>
					<p class="text-muted-foreground text-lg">Try free for 7 days. Cancel anytime.</p>
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
							<p class="text-xs text-muted-foreground">Try free for 7 days</p>
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
							href="https://github.com/float32org/calories"
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
						href="https://github.com/float32org/calories"
						target="_blank"
						rel="noopener noreferrer"
						class="hover:text-foreground transition-colors">GitHub</a
					>
					<a href={resolve('/privacy')} class="hover:text-foreground transition-colors">Privacy</a>
					<a href={resolve('/terms')} class="hover:text-foreground transition-colors">Terms</a>
				</nav>
				<p class="text-sm text-muted-foreground">
					&copy; {new Date().getFullYear()} float32
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
