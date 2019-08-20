<script>
	import StarRating from './StarRating.svelte';
	let rating = 5;
</script>

<label>
	<input type="range" name="rating" min="0" max="5" step="1" bind:value={rating}>
	Rating
</label>

<StarRating rating={rating} />