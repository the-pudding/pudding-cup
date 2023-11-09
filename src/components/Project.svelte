<script>
	export let year;
	export let award;
	export let tier;
	export let title;
	export let author;
	export let organization;
	export let link;
	export let broken;
	export let image;
	export let comment;
</script>

<li>
	<h4><a href={link}>{title}</a></h4>
	{#if author}
		<p class="byline">By {author}{#if organization}
				, {organization}
			{/if}
		</p>
	{/if}
	{#if image}
		<a href={link}>
			<img src={image} />
		</a>
	{/if}
	{#if comment}
		<p>{@html comment}</p>
	{/if}
</li>

<style>
	li {
		margin: 2rem 0;
	}
	h4 {
		font-size: var(--22px);
		font-weight: 700;
		padding: 0;
		margin: 0;
		color: var(--color-purple);
		transition: all 0.25s linear;
	}
	h4:hover {
		opacity: 0.75;
	}
	h4 a {
		color: var(--color-purple);
	}
	.byline {
		font-family: var(--sans);
	}
	p {
		padding: 0;
		margin: 0;
	}

	img {
		margin: 1rem 0;
		border: 1px solid var(--color-gray-200);
		transition: all 0.25s linear;
	}
	img:hover {
		opacity: 0.75;
	}
</style>
