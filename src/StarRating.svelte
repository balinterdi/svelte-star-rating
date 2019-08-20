<script>
  export let rating = 0;
  export let maxRating = 5;

  let numbers = [];
  for (let i=1; i < maxRating+1; i++) {
    numbers.push(i);
  }
  
  $: stars = numbers.map((n, i) => { 
    return {
      rating: i+1,
      full: Math.round(rating + 1) >= i+1
    }
  });

	// $: {
  //   console.log('[StarRating] Rating is', rating, stars.map(s => s.full ? 'F' : 'E').join(''));
  // }
</script>

{#each stars as { rating, full }}
  <span>{full ? 'F' : 'E' }</span>
{/each}