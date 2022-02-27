<script>
  'use strict';
  export let timer, minimum, better;
</script>

<p>
  {#if timer}
    {timer}
    {timer === 1 ? 'second.' : 'seconds.'}
    {timer === better ? ' Excellent!.' : timer > minimum ? ' Good.' : ''}
  {:else}
    Ready? Press START button
  {/if}
</p>

<style>
</style>
