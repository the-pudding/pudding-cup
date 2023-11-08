<script>
	import rawData from "$data/projects.csv";
	import Project from "$components/Project.svelte";

	const data = rawData.map((d) => ({
		...d,
		year: +d.year
	}));

	let year = Math.max(...data.map((d) => d.year));

	$: years = [...new Set(data.map((d) => d.year))];
	$: projects = data.filter((d) => d.year === year);
</script>

<p>Past Winners</p>
<select>
	{#each years as y}
		<option value={y}>{y}</option>
	{/each}
</select>
<ul>
	{#each projects as project}
		<Project {...project} />
	{/each}
</ul>
