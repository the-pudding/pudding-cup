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
	<h3>{title}</h3>
	<p>{author}</p>
	<p><a href={link}>View project</a></p>
</li>
