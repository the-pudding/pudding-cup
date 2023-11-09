<script>
    import ProjectList from "$components/ProjectList.svelte";

    export let projects;
    export let year;

    $: passionWinner = projects.filter((d) => d.tier === "winner" && d.award === "passion" || d.award === "staff picks");
    $: passionHM = projects.filter((d) => d.tier === "honorable mention" && d.award === "passion" || d.award === "staff picks");

    $: payWinner = projects.filter((d) => d.tier === "winner" && d.award === "pay");
    $: payHM = projects.filter((d) => d.tier === "honorable mention" && d.award === "pay");
</script>

{#if year == "2018"}
	<p class="kicker">Passion tier</p>
	<ProjectList projects={passionWinner} year={year} tier={"winner"} />
	<ProjectList projects={passionHM} year={year} tier={"honorable mention"} />
	
	<p class="kicker">Pay tier</p>
	<ProjectList projects={payWinner} year={year} tier={"winner"} />
	<ProjectList projects={payHM} year={year} tier={"honorable mention"} />
{:else}
	<ProjectList projects={passionWinner} year={year} tier={"winner"} />
	<ProjectList projects={passionHM} year={year} tier={"honorable mention"} />
{/if}

<style>
	.kicker {
		text-transform: uppercase;
		font-family: var(--sans);
		font-weight: 700;
		text-align: left;
		width: 100%;
		color: var(--color-purple);
		font-size: var(--18px);
		margin: 3rem auto 0.5rem auto;
		max-width: 40rem;
	}
</style>