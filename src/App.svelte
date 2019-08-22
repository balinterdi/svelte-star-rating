<script>
	import StarRating from './StarRating.svelte';
	let rating = 3;

	function updateRating(newRating) {
		update(newRating);
	}

	function updateRatingFromEvent(event) {
		update(event.target.value);
	}

	function update(newRating) {
		if (rating === newRating) {
			newRating = 0;
		}
		rating = newRating;
	}
</script>

<label>
	<input type="range" name="rating" min="0" max="5" step="1" value={rating} on:change={updateRatingFromEvent}>
	Rating
</label>

<StarRating rating={rating} onChange={updateRating}></StarRating>