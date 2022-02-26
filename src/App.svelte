<script>
  'use strict';
  import './main.css';
  import Handwash from './components/Handwash.svelte';
  import Handrub from './components/Handrub.svelte';

  let howTo = 0;

  const reset = () => (howTo = 0);
</script>

<main>
  <h2>Hand Hygiene</h2>
  {#if howTo === 1}
    <Handwash {reset} />
  {:else if howTo === 2}
    <Handrub {reset} />
  {:else}
    <section>
      <label>
        <input type="radio" bind:group={howTo} value={1} />
        Handwash
      </label>
      <label>
        <input type="radio" bind:group={howTo} value={2} />
        Handrub
      </label>
    </section>
  {/if}
</main>

<style>
  section {
    width: 30rem;
    display: flex;
    justify-content: space-evenly;
  }
</style>
