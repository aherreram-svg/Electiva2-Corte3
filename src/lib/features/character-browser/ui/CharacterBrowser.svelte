<script lang="ts">
	import { CharacterList } from '$lib/features/character-list';
	import { CharacterSearch } from '$lib/features/character-search';
	import type { CharacterBrowserData } from '../model';

	export let data: CharacterBrowserData;
	export let onQueryChange: (value: string) => void;
</script>

<section class="hero">
	<div class="eyebrow">SvelteKit · Rick and Morty</div>
	<h1>Explorador visual de personajes</h1>
	<p>
		Una interfaz mas limpia para consultar personajes en tiempo real, con una presentacion enfocada en
		claridad, ritmo visual y lectura rapida.
	</p>
</section>

<div class="panel">
	<CharacterSearch query={data.query} onQueryChange={onQueryChange} />

	<div class="meta">
		<p class="results">{data.total} personajes encontrados</p>
		{#if data.error}
			<p class="error">{data.error}</p>
		{:else}
			<p class="status">Busqueda conectada con la API</p>
		{/if}
	</div>

	<CharacterList characters={data.characters} />
</div>

<style>
	section.hero {
		max-width: 960px;
		margin: 0 auto;
		padding: 4.75rem 1.25rem 1.75rem;
	}

	.eyebrow {
		display: inline-flex;
		padding: 0.45rem 0.8rem;
		border-radius: 999px;
		border: 1px solid rgba(37, 99, 235, 0.12);
		background: rgba(37, 99, 235, 0.08);
		color: #1d4ed8;
		font-weight: 700;
		font-size: 0.8rem;
		letter-spacing: 0.08em;
		text-transform: uppercase;
	}

	h1 {
		max-width: 10ch;
		margin: 1rem 0 1rem;
		font-size: clamp(2.8rem, 7vw, 5.1rem);
		line-height: 0.92;
		letter-spacing: -0.04em;
	}

	p {
		max-width: 58ch;
		margin: 0;
		color: #475569;
		font-size: 1.04rem;
		line-height: 1.75;
	}

	.panel {
		max-width: 960px;
		margin: 0 auto;
		padding: 0 1.25rem 3rem;
		display: grid;
		gap: 1.15rem;
	}

	.meta {
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		gap: 1rem;
		align-items: center;
		padding: 0 0.2rem;
	}

	.meta p {
		margin: 0;
		font-size: 0.95rem;
	}

	.results {
		color: #0f172a;
		font-weight: 700;
	}

	.status {
		padding: 0.45rem 0.7rem;
		border-radius: 999px;
		background: rgba(22, 163, 74, 0.12);
		color: #15803d;
	}

	.error {
		padding: 0.45rem 0.7rem;
		border-radius: 999px;
		background: rgba(239, 68, 68, 0.12);
		color: #b91c1c;
	}

	@media (max-width: 640px) {
		section.hero {
			padding-top: 3.5rem;
		}

		h1 {
			max-width: 12ch;
		}
	}
</style>
