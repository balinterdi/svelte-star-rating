<script>
  export let rating = 0;
  export let maxRating = 5;
  
  function stars() {
    let starsArray = [];
    for (let i=1; i <= maxRating; i++) {
      starsArray.push({ rating: i, full: Math.round(rating) >= i });
    }
    return starsArray;
  }
</script>

{#each stars() as { rating, full }}
  <span>{full ? 'F' : 'E' }</span>
{/each}