<script lang="ts">
	import { prompt, resume } from '$lib/resume';
</script>

<section id="services" class="man-section container" aria-labelledby="services-title">
	<p class="section-cmd" aria-hidden="true">{prompt} <span class="cmd">services</span></p>
	<h2 id="services-title">How we can help</h2>
	<div class="man-body grid">
		{#each resume.services as service (service.title)}
			<article class="service">
				<h3><span class="marker" aria-hidden="true">+</span>{service.title}</h3>
				<p class="description">{service.description}</p>
				<ul aria-label="Typical deliverables">
					{#each service.deliverables as deliverable (deliverable)}
						<li>{deliverable}</li>
					{/each}
				</ul>
			</article>
		{/each}
	</div>
</section>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));
		gap: 1.1rem;
	}

	.service {
		padding: 1.25rem;
		border: 1px solid var(--color-line);
		border-radius: 6px;
		background: linear-gradient(145deg, var(--color-raised), var(--color-panel));
	}

	h3 {
		color: var(--color-green);
		font-size: 1rem;
	}

	.marker {
		margin-right: 0.45rem;
		color: var(--color-amber);
	}

	.description {
		margin-top: 0.7rem;
		color: var(--color-text);
		font-size: 0.9rem;
	}

	ul {
		margin-top: 1rem;
		padding-top: 0.85rem;
		border-top: 1px dashed var(--color-line);
		color: var(--color-muted);
		font-size: 0.82rem;
	}

	li {
		margin-top: 0.35rem;
	}

	li::before {
		content: '→ ';
		color: var(--color-dim);
	}

	@media (max-width: 850px) {
		.grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
		}
	}

	@media (max-width: 560px) {
		.grid {
			grid-template-columns: minmax(0, 1fr);
		}
	}
</style>
