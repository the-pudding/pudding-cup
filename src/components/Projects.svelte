<script>
	import rawData from "$data/projects.csv";
	import Project from "$components/Project.svelte";
	import ProjectGroup from "$components/ProjectGroup.svelte";

	const data = rawData.map((d) => ({
		...d,
		year: +d.year
	}));

	let selected;
	let year = Math.max(...data.map((d) => d.year));

	$: years = [...new Set(data.map((d) => d.year))];
	$: projects = data.filter((d) => d.year === selected);
</script>

<div class="past-select">
	<p>See past winners from</p>
	<select bind:value={selected}>
		{#each years as y}
			<option value={y}>{y}</option>
		{/each}
	</select>
</div>

<ProjectGroup projects={projects} year={selected} />

<style>
	.past-select {
		position: sticky;
		top: 0;
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		background: var(--color-gray-100);
		padding: 1rem 0;
		border-bottom: 1px solid var(--color-gray-200);
		z-index: 1000;
	}
	p {
		font-family: var(--sans);
		padding: 0;
		margin: 0;
	}
	select {
		margin: 0 0 0 0.5rem;
		font-weight: 700;
	}
</style>
