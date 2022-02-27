<script>
  'use strict';
  import Buttons from './Buttons.svelte';
  import ProgressBar from './ProgressBar.svelte';
  import Timer from './Timer.svelte';

  export let title, src, minimum, better, reset;

  const origin = 'World Health Organization',
    path = 'https://www.who.int/campaigns/world-hand-hygiene-day';

  let timer = 0,
    progress = 0,
    color = null,
    interval = null;

  const stop = () => {
    clearInterval(interval);
    reset();
  };

  const start = () => {
    interval = setInterval(() => {
      timer >= minimum ? (color = 'lightskyblue') : (color = 'lightblue');
      if (timer === better) stop();
      else timer = timer + 1;
      progress = timer;
    }, 1000);
  };

  $: if (timer !== 0) {
    progress = 100 - ((better - timer) / better) * 100;
  }
</script>

<h3>{title}</h3>
{#if title === 'Handwash'}
  <p>Wash hands when visibly soiled! otherwise, use handrub.</p>
{/if}
{#if title === 'Handrub'}
  <p>Rub hands for hand hygiene! wash hands when visibly soiled.</p>
{/if}
<Timer {timer} {minimum} {better} />
<Buttons {timer} {reset} {start} {minimum} />
<ProgressBar {progress} {color} />
<p>Duration of the entire procedure: {minimum}-{better} seconds.</p>
<figure>
  <img {src} alt={title} />
  <figcaption>
    Taken from <a href={path} target="_blank" rel="noopener noreferrer"
      >{origin}</a
    >
  </figcaption>
</figure>

<style>
  figcaption {
    font-size: smaller;
    color: ligh;
  }
</style>
