<script>
  'use strict';
  export let timer;
</script>

<p>
  {#if timer}
    {timer} {timer === 1 ? 'second' : 'seconds'}
  {:else}
    Ready? Press START button
  {/if}
</p>

<style>
</style>
