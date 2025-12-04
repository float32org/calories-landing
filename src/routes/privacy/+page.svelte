<script lang="ts">
	import { resolve } from '$app/paths';
	import { PUBLIC_APP_URL } from '$env/static/public';
	import { Button } from '$lib/components/ui/button';
	import Hamburger from '@lucide/svelte/icons/hamburger';
	import Moon from '@lucide/svelte/icons/moon';
	import Sun from '@lucide/svelte/icons/sun';
	import { toggleMode } from 'mode-watcher';
</script>

<svelte:head>
	<title>Privacy Policy - Calories</title>
	<meta
		name="description"
		content="Learn how Calories collects, uses, and protects your personal information. We're committed to keeping your nutrition data secure."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Privacy Policy - Calories" />
	<meta
		property="og:description"
		content="Learn how Calories collects, uses, and protects your personal information."
	/>
	<meta property="og:url" content="https://burncalories.app/privacy" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="Privacy Policy - Calories" />
	<meta
		name="twitter:description"
		content="Learn how Calories collects, uses, and protects your personal information."
	/>
</svelte:head>

<div class="flex min-h-screen flex-col bg-background">
	<header class="py-4">
		<div class="container mx-auto flex items-center justify-between px-4 md:px-6">
			<a href={resolve('/')} class="flex items-center gap-2 font-medium text-xl">
				<div
					class="size-8 rounded-lg bg-primary flex items-center justify-center text-primary-foreground"
				>
					<Hamburger class="size-5" />
				</div>
				Calories
			</a>
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
		<div class="container mx-auto max-w-3xl px-4 py-12 md:py-16">
			<h1 class="text-3xl font-bold mb-2">Privacy Policy</h1>
			<p class="text-muted-foreground mb-8">Last updated: December 2025</p>
			<div class="prose max-w-none space-y-8">
				<section>
					<h2 class="text-xl font-semibold mb-3">Overview</h2>
					<p class="text-muted-foreground">
						Calories ("we", "our", or "us") is operated by float32 LLC. This Privacy Policy explains
						how we collect, use, and protect your information when you use our nutrition tracking
						application at burncalories.app.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Information We Collect</h2>
					<p class="text-muted-foreground mb-3">We collect information you provide directly:</p>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>
							<strong class="text-foreground">Account information:</strong> Email address and authentication
							data
						</li>
						<li>
							<strong class="text-foreground">Health & nutrition data:</strong> Meals logged, calorie
							intake, macronutrients (protein, carbs, fat), weight measurements, water intake, and fitness
							goals
						</li>
						<li>
							<strong class="text-foreground">Food photos:</strong> Images you upload for AI meal analysis
						</li>
						<li>
							<strong class="text-foreground">Preferences:</strong> Dietary preferences, food likes/dislikes,
							measurement units
						</li>
						<li>
							<strong class="text-foreground">Payment information:</strong> Processed securely by Stripe
							(we do not store card details)
						</li>
					</ul>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">How We Use Your Information</h2>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>Provide and improve our nutrition tracking services</li>
						<li>Analyze food photos and descriptions using AI to estimate nutritional content</li>
						<li>Personalize meal suggestions based on your preferences and goals</li>
						<li>Process subscription payments</li>
						<li>Send important service updates (not marketing)</li>
					</ul>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">AI & Third-Party Services</h2>
					<p class="text-muted-foreground mb-3">We use the following third-party services:</p>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>
							<strong class="text-foreground">AI Services:</strong> Food photos and descriptions are processed
							by AI providers to estimate nutritional content. This data is used solely for analysis and
							is not used to train AI models.
						</li>
						<li>
							<strong class="text-foreground">Stripe:</strong> Handles all payment processing
							securely. See
							<a
								href="https://stripe.com/privacy"
								target="_blank"
								rel="noopener noreferrer"
								class="text-primary hover:underline">Stripe's Privacy Policy</a
							>.
						</li>
						<li>
							<strong class="text-foreground">Authentication:</strong> We use secure authentication services
							to manage your account.
						</li>
					</ul>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Data Storage & Security</h2>
					<p class="text-muted-foreground">
						Your data is stored securely using industry-standard encryption. We implement
						appropriate technical and organizational measures to protect your personal information
						against unauthorized access, alteration, or destruction.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Your Rights</h2>
					<p class="text-muted-foreground mb-3">You have the right to:</p>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>Access your personal data</li>
						<li>Correct inaccurate data</li>
						<li>Delete your account and associated data</li>
						<li>Export your data</li>
						<li>Cancel your subscription at any time</li>
					</ul>
					<p class="text-muted-foreground mt-3">
						You can delete your account directly in the app settings, which will remove all your
						personal data.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Data Retention</h2>
					<p class="text-muted-foreground">
						We retain your data for as long as your account is active. When you delete your account,
						we delete your personal data within 30 days, except where we're required to retain it
						for legal purposes.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Children's Privacy</h2>
					<p class="text-muted-foreground">
						Calories is not intended for children under 13. We do not knowingly collect personal
						information from children under 13.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Changes to This Policy</h2>
					<p class="text-muted-foreground">
						We may update this Privacy Policy from time to time. We will notify you of any material
						changes by posting the new policy on this page and updating the "Last updated" date.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Contact Us</h2>
					<p class="text-muted-foreground">
						If you have questions about this Privacy Policy, please contact us at:
						<a href="mailto:support@burncalories.app" class="text-primary hover:underline"
							>support@burncalories.app</a
						>
					</p>
				</section>
			</div>
		</div>
	</main>
</div>
