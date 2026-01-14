<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<!-- If Parkinsans is a Google Font, uncomment and update the URL below -->
	<!-- <link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Parkinsans:wght@400;500;600;700&display=swap" rel="stylesheet"> -->
</svelte:head>

{@render children()}
