<script lang="ts">
	import { resolve } from '$app/paths';
	import { page } from '$app/state';
	import { PUBLIC_APP_URL } from '$env/static/public';
	import { Button } from '$lib/components/ui/button';
	import AlertCircleIcon from '@lucide/svelte/icons/alert-circle';
	import HamburgerIcon from '@lucide/svelte/icons/hamburger';
	import Moon from '@lucide/svelte/icons/moon';
	import Sun from '@lucide/svelte/icons/sun';
	import { toggleMode } from 'mode-watcher';

	const errors: Record<number, { title: string; message: string }> = {
		404: { title: 'Page Not Found', message: "The page you're looking for doesn't exist." },
		500: { title: 'Server Error', message: 'Something went wrong on our end.' }
	};

	const errorInfo = $derived(
		errors[page.status] || {
			title: 'Something Went Wrong',
			message: page.error?.message || 'An unexpected error occurred.'
		}
	);
</script>

<svelte:head>
	<title>{errorInfo.title} - Calories</title>
	<meta name="robots" content="noindex" />
</svelte:head>

<div class="flex min-h-screen flex-col">
	<header class="py-4">
		<div class="container mx-auto flex items-center justify-between px-4 md:px-6">
			<a href={resolve('/')} class="flex items-center gap-2 font-medium text-xl">
				<div
					class="size-8 rounded-lg bg-primary flex items-center justify-center text-primary-foreground"
				>
					<HamburgerIcon class="size-5" />
				</div>
				Calories
			</a>
			<nav class="hidden md:flex items-center gap-6 text-sm font-medium text-muted-foreground">
				<a href="/#features" class="hover:text-foreground transition-colors">Features</a>
				<a href="/#pricing" class="hover:text-foreground transition-colors">Pricing</a>
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

	<main class="flex flex-1 flex-col items-center justify-center px-6">
		<div class="mx-auto flex w-full max-w-md flex-col items-center text-center">
			<div class="mb-4 flex size-16 items-center justify-center rounded-full bg-muted">
				<AlertCircleIcon class="size-8 text-muted-foreground" />
			</div>

			<p class="mb-1 text-sm font-medium text-muted-foreground">Error {page.status}</p>

			<h1 class="mb-2 text-xl font-bold tracking-tight">
				{errorInfo.title}
			</h1>

			<p class="mb-8 text-sm text-muted-foreground">
				{errorInfo.message}
			</p>

			<div class="flex gap-3">
				<Button variant="outline" onclick={() => window.location.reload()}>Try again</Button>
				<Button href={resolve('/')}>Go home</Button>
			</div>
		</div>
	</main>
</div>
