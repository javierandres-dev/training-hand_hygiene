<script>
  'use strict';
  import BackBtn from './BackBtn.svelte';
  import ProgressBar from './ProgressBar.svelte';
  import StartBtn from './StartBtn.svelte';
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
    (timer = 0), (progress = 0), (color = null), (interval = null);
    reset();
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
  }
</script>

<h3>{title}</h3>
<BackBtn {timer} {reset} />
<ProgressBar {progress} {color} />
<Timer {timer} />
<StartBtn {start} {timer} />
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
  p {
    font-size: small;
  }
  figcaption {
    font-size: smaller;
  }
</style>
