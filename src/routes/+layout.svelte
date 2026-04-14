<svelte:head>
	<title>Prueba Lectiva</title>
	<meta
		name="description"
		content="Base SvelteKit con arquitectura feature-first/domain-first para integrar Rick and Morty."
	/>
</svelte:head>

<div class="app-shell">
	<slot />
</div>

<style>
	:global(html) {
		color-scheme: light;
	}

	:global(body) {
		margin: 0;
		font-family:
			Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
		background:
			radial-gradient(circle at top left, rgba(37, 99, 235, 0.12), transparent 30%),
			radial-gradient(circle at top right, rgba(250, 204, 21, 0.14), transparent 22%),
			linear-gradient(180deg, #f8fafc 0%, #eef4ff 100%);
		color: #0f172a;
		min-height: 100vh;
	}

	.app-shell {
		min-height: 100vh;
	}
</style>
