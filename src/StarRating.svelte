<script>
  import Icon from 'fa-svelte';
  import { faStar as starIcon } from '@fortawesome/free-solid-svg-icons/faStar';
  import { faStar as emptyStarIcon } from '@fortawesome/free-regular-svg-icons/faStar';

  export let rating = 0;
  export let maxRating = 5;
  export let onChange = () => {};

  let numbers = [];
  for (let i=1; i < maxRating+1; i++) {
    numbers.push(i);
  }
  
  $: stars = numbers.map((n, i) => { 
    return {
      rating: i+1,
      full: Math.round(rating) >= i+1
    }
  });

	// $: {
  //   console.log('[StarRating] Rating is', rating, stars.map(s => s.full ? 'F' : 'E').join(''));
  // }
</script>

<style>
  button {
    border: 0;
    padding: 0;
    margin: 0;
    background: none;
    cursor: pointer;
  }

  button + button {
    margin-left: .1rem;
  }
</style>

{#each stars as { rating: r, full }}
  <!-- <i class="{full ? 'fas' : 'far'} fa-star"></i> -->
  <button type="button" on:click={() => onChange(r)}>
    <Icon icon={full ? starIcon : emptyStarIcon}></Icon>
  </button>
{/each}