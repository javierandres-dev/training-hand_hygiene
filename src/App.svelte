<script>
  import ProgressBar from './components/ProgressBar.svelte';
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
  }
</script>

<h2>Handwashing</h2>
<p>Duration of the entire procedure: 40-60 seconds</p>
<ProgressBar {progress} {color} {timer} />
<p>
  {#if timer}
    {timer} {timer === 1 ? 'second' : 'seconds'}
  {:else}
    Ready? Press START button
  {/if}
</p>
<button on:click={start}>START</button>
