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
	<title>Terms of Service - Calories</title>
	<meta
		name="description"
		content="Read the Terms of Service for Calories, the AI-powered nutrition tracking app. Learn about subscriptions, acceptable use, and your rights."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Terms of Service - Calories" />
	<meta
		property="og:description"
		content="Read the Terms of Service for Calories, the AI-powered nutrition tracking app."
	/>
	<meta property="og:url" content="https://burncalories.app/terms" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="Terms of Service - Calories" />
	<meta
		name="twitter:description"
		content="Read the Terms of Service for Calories, the AI-powered nutrition tracking app."
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
			<h1 class="text-3xl font-bold mb-2">Terms of Service</h1>
			<p class="text-muted-foreground mb-8">Last updated: December 2025</p>
			<div class="prose prose-neutral dark:prose-invert max-w-none space-y-8">
				<section>
					<h2 class="text-xl font-semibold mb-3">Agreement to Terms</h2>
					<p class="text-muted-foreground">
						By accessing or using Calories ("the Service"), operated by float32 LLC, you agree to be
						bound by these Terms of Service. If you do not agree to these terms, please do not use
						the Service.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Description of Service</h2>
					<p class="text-muted-foreground">
						Calories is a nutrition tracking application that allows you to log meals, track
						calories and macronutrients, monitor weight and water intake, and receive AI-powered
						nutritional insights. The Service is available at burncalories.app.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Account Registration</h2>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>You must provide accurate and complete information when creating an account</li>
						<li>You are responsible for maintaining the security of your account credentials</li>
						<li>You must be at least 13 years old to use the Service</li>
						<li>One person may not maintain more than one account</li>
					</ul>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Subscription & Billing</h2>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>
							<strong class="text-foreground">Free Trial:</strong> New users receive a 7-day free trial
							of Calories Pro
						</li>
						<li>
							<strong class="text-foreground">Pricing:</strong> After the trial, Calories Pro is $3/month
						</li>
						<li>
							<strong class="text-foreground">Billing:</strong> Subscriptions are billed monthly through
							Stripe
						</li>
						<li>
							<strong class="text-foreground">Cancellation:</strong> You may cancel your subscription
							at any time. You'll retain access until the end of your current billing period
						</li>
						<li>
							<strong class="text-foreground">Refunds:</strong> We generally do not provide refunds, but
							you can contact us for exceptional circumstances
						</li>
					</ul>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Acceptable Use</h2>
					<p class="text-muted-foreground mb-3">You agree not to:</p>
					<ul class="list-disc list-inside space-y-2 text-muted-foreground">
						<li>Use the Service for any illegal purpose</li>
						<li>Upload malicious content or attempt to compromise the Service</li>
						<li>Share your account credentials with others</li>
						<li>Attempt to reverse engineer or extract source code from the Service</li>
						<li>Use automated systems to access the Service without permission</li>
						<li>Resell or redistribute the Service</li>
					</ul>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">AI-Powered Features</h2>
					<p class="text-muted-foreground">
						The Service uses artificial intelligence to analyze food photos and provide nutritional
						estimates. While we strive for accuracy, AI estimates are approximations and should not
						be relied upon for medical or dietary decisions requiring precision. Always consult
						healthcare professionals for medical nutrition advice.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Health Disclaimer</h2>
					<p class="text-muted-foreground">
						Calories is a tracking tool and does not provide medical advice. The nutritional
						information, suggestions, and AI insights are for informational purposes only. Consult a
						qualified healthcare provider or registered dietitian before making significant changes
						to your diet, especially if you have health conditions.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Intellectual Property</h2>
					<p class="text-muted-foreground">
						The Service, including its design, features, and content, is owned by float32 LLC and
						protected by intellectual property laws. You retain ownership of the data you input
						(meals, photos, etc.), and grant us a license to use it solely to provide the Service to
						you.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Limitation of Liability</h2>
					<p class="text-muted-foreground">
						To the maximum extent permitted by law, float32 LLC shall not be liable for any
						indirect, incidental, special, consequential, or punitive damages resulting from your
						use of the Service. Our total liability shall not exceed the amount you paid us in the
						12 months preceding the claim.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Service Availability</h2>
					<p class="text-muted-foreground">
						We strive to maintain high availability but do not guarantee uninterrupted access. We
						may modify, suspend, or discontinue features with reasonable notice when possible. We
						reserve the right to terminate accounts that violate these terms.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Changes to Terms</h2>
					<p class="text-muted-foreground">
						We may update these Terms from time to time. We will notify you of material changes via
						email or through the Service. Continued use after changes constitutes acceptance of the
						new terms.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Governing Law</h2>
					<p class="text-muted-foreground">
						These Terms shall be governed by the laws of the United States. Any disputes shall be
						resolved in the courts of competent jurisdiction.
					</p>
				</section>
				<section>
					<h2 class="text-xl font-semibold mb-3">Contact Us</h2>
					<p class="text-muted-foreground">
						If you have questions about these Terms, please contact us at:
						<a href="mailto:support@burncalories.app" class="text-primary hover:underline"
							>support@burncalories.app</a
						>
					</p>
				</section>
			</div>
		</div>
	</main>
</div>
