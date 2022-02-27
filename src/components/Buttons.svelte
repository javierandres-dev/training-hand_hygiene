<script>
  'use strict';
  import BackBtn from './BackBtn.svelte';
  import StartBtn from './StartBtn.svelte';

  export let timer, reset, start, minimum;
</script>

<section>
  <BackBtn {timer} {reset} {minimum} />
  <StartBtn {timer} {start} />
</section>

<style>
  section {
    display: flex;
    gap: 1rem;
    margin-bottom: 1rem;
  }
</style>
