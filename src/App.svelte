<script>
  import Handwash from './components/Handwash.svelte';
  import Handrub from './components/Handrub.svelte';
  ('use strict');

  let howTo = 0;
  /*   import ProgressBar from './components/ProgressBar.svelte';
  let better = 60,
    minimum = 40,
    timer = 0,
    interval = null,
    progress = 0,
    color = null;

  const stop = () => {
    clearInterval(interval);
    timer = 0;
  };

  const start = () => {
    interval = setInterval(() => {
      timer >= minimum ? (color = 'green') : (color = 'yellow');
      if (timer === better) stop();
      else timer = timer + 1;
      progress = timer;
    }, 1000);
  };

  $: if (timer !== 0) {
    progress = 100 - ((better - timer) / better) * 100;
    console.log('timer :>> ', timer);
    console.log('progress :>> ', progress);
  } */
</script>

<h2>Hand Hygiene</h2>
{#if howTo === 1}
  <Handwash />
{:else if howTo === 2}
  <Handrub />
{:else}
  <label>
    <input type="radio" bind:group={howTo} value={1} />
    Handwash
  </label>
  <label>
    <input type="radio" bind:group={howTo} value={2} />
    Handrub
  </label>
{/if}

<!-- <ProgressBar {progress} {color} {timer} />
<p>
  {#if timer}
    {timer} {timer === 1 ? 'second' : 'seconds'}
  {:else}
    Ready? Press START button
  {/if}
</p>
<button on:click={start}>START</button> -->
