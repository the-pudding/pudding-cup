<script>
	export let year;
	export let award;
	export let tier;
	export let title;
	export let author;
	export let organization;
	export let link;
	export let image;
	export let comment;
	export let alt;
</script>

<li>
	<h4><a href={link}>{title}</a></h4>
	{#if author}
		<p class="byline">
			By: {@html author}
			{#if organization}&mdash; {@html organization}{/if}
		</p>
	{/if}
	{#if image}
		<a href={link} target="_blank" rel="noreferrer">
			<img src={image} alt={alt} />
		</a>
	{/if}
	{#if comment}
		<p>{@html comment}</p>
	{/if}
</li>

<style>
	li {
		margin: 32px 0;
	}
	h4 {
		font-size: var(--22px);
		font-weight: 700;
		padding: 0;
		margin: 0;
		margin-bottom: 4px;
		color: var(--color-purple);
		transition: all 0.25s linear;
		display: inline-block;
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
	:global(.byline a:hover, p a:hover) {
		opacity: 0.5;
	}
	p {
		padding: 0;
		margin: 0;
	}
	img {
		margin: 16px 0;
		border: 1px solid var(--color-gray-200);
		transition: all 0.25s linear;
	}
	img:hover {
		opacity: 0.75;
	}
</style>
