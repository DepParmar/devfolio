<script lang="ts">
	import { prompt, resume } from '$lib/resume';
</script>

<section id="domains" class="man-section container" aria-labelledby="domains-title">
	<p class="section-cmd" aria-hidden="true">{prompt} <span class="cmd">domains</span></p>
	<h2 id="domains-title">Domains we understand</h2>
	<div class="man-body grid">
		{#each resume.domains as domain, index (domain.name)}
			<article class="domain">
				<p class="index" aria-hidden="true">0{index + 1}</p>
				<h3>{domain.name}</h3>
				<p>{domain.description}</p>
			</article>
		{/each}
	</div>
</section>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(5, minmax(0, 1fr));
		gap: 0.75rem;
	}

	.domain {
		min-height: 10rem;
		padding: 1rem;
		border-top: 2px solid var(--color-line-strong);
		background: var(--color-panel);
	}

	.domain:hover {
		border-top-color: var(--color-amber);
	}

	.index {
		color: var(--color-amber);
		font-size: 0.78rem;
	}

	h3 {
		margin-top: 1.15rem;
		color: var(--color-green);
		font-size: 0.92rem;
	}

	.domain p:last-child {
		margin-top: 0.55rem;
		color: var(--color-muted);
		font-size: 0.8rem;
		line-height: 1.55;
	}

	@media (max-width: 980px) {
		.grid {
			grid-template-columns: repeat(3, minmax(0, 1fr));
		}
	}

	@media (max-width: 620px) {
		.grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
		}
	}

	@media (max-width: 400px) {
		.grid {
			grid-template-columns: minmax(0, 1fr);
		}
	}
</style>
