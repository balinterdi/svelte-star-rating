<script>
	import StarRating from './StarRating.svelte';
	let rating = 3;

	// $: console.log('[App] Rating is', rating);
	function updateRating(newRating) {
		rating = newRating;
	}

	function updateRatingFromEvent(event) {
		rating = event.target.value;
	}
</script>

<label>
	<input type="range" name="rating" min="0" max="5" step="1" value={rating} on:change={updateRatingFromEvent}>
	Rating
</label>

<StarRating rating={rating} onChange={updateRating}></StarRating>