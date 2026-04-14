<script lang="ts">
	export let query: string = '';
	export let onQueryChange: (value: string) => void;
</script>

<section class="search-card">
	<div class="search-copy">
		<div class="badge">Busqueda en vivo</div>
		<div>
			<h2>Encuentra personajes al instante</h2>
			<p>Filtra por nombre y explora resultados con una interfaz mas clara, ligera y facil de escanear.</p>
		</div>
	</div>

	<label class="search-field" for="character-search">
		<span>Buscar personaje</span>
		<div class="input-shell">
			<svg viewBox="0 0 24 24" aria-hidden="true">
				<path
					d="M10.5 4a6.5 6.5 0 1 0 4.03 11.6l4.43 4.44 1.06-1.06-4.44-4.43A6.5 6.5 0 0 0 10.5 4Zm0 1.5a5 5 0 1 1 0 10 5 5 0 0 1 0-10Z"
				/>
			</svg>
			<input
				id="character-search"
				type="search"
				placeholder="Rick, Morty, Summer..."
				value={query}
				on:input={(event) => onQueryChange((event.currentTarget as HTMLInputElement).value)}
			/>
			<div class="hint">API live</div>
		</div>
	</label>
</section>

<style>
	.search-card {
		display: grid;
		gap: 1.25rem;
		padding: 1.35rem;
		border: 1px solid #dce7f5;
		border-radius: 24px;
		background:
			linear-gradient(135deg, rgba(238, 244, 255, 0.9), rgba(248, 250, 252, 0.98)),
			#ffffff;
		box-shadow: 0 24px 50px rgba(37, 99, 235, 0.08);
	}

	.search-copy {
		display: grid;
		gap: 0.55rem;
	}

	.badge {
		width: fit-content;
		padding: 0.38rem 0.75rem;
		border-radius: 999px;
		background: rgba(250, 204, 21, 0.22);
		color: #92400e;
		font-size: 0.74rem;
		font-weight: 700;
		letter-spacing: 0.08em;
		text-transform: uppercase;
	}

	h2 {
		margin: 0;
		font-size: clamp(1.35rem, 2vw, 1.8rem);
		line-height: 1.05;
		color: #0f172a;
	}

	p {
		margin: 0.45rem 0 0;
		max-width: 58ch;
		color: #475569;
		font-size: 0.98rem;
		line-height: 1.6;
	}

	.search-field {
		display: grid;
		gap: 0.65rem;
	}

	.search-field span {
		font-size: 0.92rem;
		font-weight: 600;
		color: #334155;
	}

	.input-shell {
		display: grid;
		grid-template-columns: auto 1fr auto;
		align-items: center;
		gap: 0.85rem;
		padding: 0.35rem 0.4rem 0.35rem 0.9rem;
		border: 1px solid #dce7f5;
		border-radius: 18px;
		background: rgba(255, 255, 255, 0.96);
		box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.65);
		transition:
			border-color 0.2s ease,
			box-shadow 0.2s ease,
			transform 0.2s ease;
	}

	.input-shell:focus-within {
		border-color: #2563eb;
		box-shadow:
			0 0 0 4px rgba(37, 99, 235, 0.12),
			0 16px 32px rgba(37, 99, 235, 0.12);
		transform: translateY(-1px);
	}

	svg {
		width: 1.15rem;
		height: 1.15rem;
		fill: #2563eb;
	}

	input {
		width: 100%;
		box-sizing: border-box;
		border: 0;
		background: transparent;
		color: #0f172a;
		padding: 0.95rem 0;
		outline: none;
		font-size: 1rem;
	}

	input::placeholder {
		color: #94a3b8;
	}

	.hint {
		padding: 0.6rem 0.8rem;
		border-radius: 14px;
		background: rgba(22, 163, 74, 0.12);
		color: #15803d;
		font-size: 0.78rem;
		font-weight: 700;
		letter-spacing: 0.04em;
		text-transform: uppercase;
	}

	@media (max-width: 640px) {
		.search-card {
			padding: 1.1rem;
			border-radius: 20px;
		}

		.input-shell {
			grid-template-columns: auto 1fr;
			padding-right: 0.35rem;
		}

		.hint {
			grid-column: 1 / -1;
			width: fit-content;
		}
	}
</style>
