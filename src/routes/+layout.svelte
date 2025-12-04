<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import { ModeWatcher } from 'mode-watcher';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Geist+Mono:wght@400;500;600;700&display=swap"
		rel="stylesheet"
	/>
	<meta property="og:type" content="website" />
	<meta property="og:site_name" content="Calories" />
	<meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<ModeWatcher />
{@render children()}
