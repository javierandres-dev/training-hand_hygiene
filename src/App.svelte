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
    <p>Wash hands when visibly soiled, rub hands for hand hygiene.</p>
    <section>
      <div>
        <input type="radio" id="handwash" bind:group={howTo} value={1} />
        <label for="handwash"> Handwash </label>
      </div>
      <div>
        <input type="radio" id="handrub" bind:group={howTo} value={2} />
        <label for="handrub"> Handrub </label>
      </div>
    </section>
  {/if}
</main>
<footer>
  <p>
    <a href="http://javierandres.dev" target="_blank" rel="noopener noreferrer">
      By Javier Andrés | Software Developer
    </a>
  </p>
</footer>

<style>
  section {
    width: 30rem;
    margin: auto;
    display: flex;
    justify-content: space-evenly;
  }
  footer {
    text-align: end;
    font-size: 1rem;
    padding: 1rem;
  }
</style>
