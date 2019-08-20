<script>
	import StarRating from './StarRating.svelte';
	let rating = 3;

	// $: console.log('[App] Rating is', rating);
</script>

<label>
	<input type="range" name="rating" min="0" max="5" step="1" bind:value={rating}>
	Rating
</label>

<StarRating rating={rating} />