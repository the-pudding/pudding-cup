<script>
	import { getContext } from "svelte";
	import Projects from "$components/Projects.svelte";
	import Footer from "$components/Footer.svelte";

	const copy = getContext("copy");
</script>

<section class="intro">
	<h1>{copy.title}</h1>
	<p class="desc">{copy.description}</p>
</section>

<section class="details">
	{#each copy.prelude as graf}
		<p class="graf">{graf.value}</p>
	{/each}
	<ul>
		{#each copy.details as bullet}
			<li>{@html bullet.value}</li>
		{/each}
	</ul>
	<a href={copy} class="btn submit">Submit</a>

	<p class="note">*{copy.commercial}</p>
</section>

<section class="projects">
	<Projects />
</section>

<Footer />

<style>
	section {
		padding: 0 1rem 4rem 1rem;
		margin: 0 auto;
		width: 100%;
		max-width: 40rem;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	h1 {
		font-family: var(--sans);
		font-size: var(--48px);
		font-weight: 900;
		text-align: center;
		line-height: 1;
	}

	.desc {
		font-family: var(--sans);
	}
	.note {
		font-family: var(--sans);
		font-size: var(--14px);
		color: var(--color-gray-700);
	}
	ul {
		margin: 16px 0;
		list-style-type: square;
		width: 100%;
	}
	.submit {
		background: var(--color-purple);
		color: white;
		font-weight: 700;
		padding: 1rem 2rem;
		margin: 2rem 0;
		transition: all 0.25s linear;
	}
	.submit:hover {
		background: var(--color-gray-1000);
	}
	.projects {
		width: 100%;
		max-width: none;
		border-top: 1px solid var(--color-gray-200);
		background: var(--color-gray-100)
	}

	@media (min-width: 800px) {
		h1 {
			font-size: var(--64px);
		}
	}
</style>
