<script>
	import Project from "$components/Project.svelte";

	export let projects;
	export let tier;
	export let year;

	const groupTitle = tier == "winner" ? `The ${year} winners` : `Honorable ${year} mentions`;
</script>

<div>
	<h3>{groupTitle}</h3>
	<ul>
		{#each projects as project}
			<Project {...project} />
		{/each}
	</ul>
</div>

<style>
	div {
		max-width: 40rem;
		margin: 0 auto;
		width: 100%;
	}
	h3 {
		font-family: var(--serif);
		font-size: var(--36px);
		font-weight: 700;
		margin: 0;
		padding: 1rem 0 0 0;
	}

	ul {
		list-style: none;
		padding: 0;
	}
</style>
