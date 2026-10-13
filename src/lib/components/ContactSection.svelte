<script lang="ts">
	import { prompt, resume } from '$lib/resume';
</script>

<section id="contact" class="man-section container" aria-labelledby="contact-title">
	<p class="section-cmd" aria-hidden="true">{prompt} <span class="cmd">contact</span></p>
	<h2 id="contact-title">Contact</h2>
	<div class="man-body">
		<p class="lede">{resume.contactLede}</p>
		<ul class="socials">
			{#each resume.socials as social (social.href)}
				<li>
					<a class="bracket-link" href={social.href} target="_blank" rel="noreferrer"
						>{social.label.toLowerCase()}</a
					>
				</li>
			{/each}
		</ul>
		<p class="location">{resume.location}</p>
	</div>
</section>

<style>
	.lede {
		max-width: 60ch;
	}

	.socials {
		display: flex;
		flex-wrap: wrap;
		gap: 1.1rem;
		margin-top: 1.2rem;
	}

	.location {
		margin-top: 1.1rem;
		color: var(--color-dim);
		font-size: 0.9rem;
	}
</style>
