<script>
  'use strict';
  export let reset, timer;
</script>

<button on:click={reset} disabled={timer !== 0}>Back</button>

<style>
  button {
    width: 100%;
  }
  button:hover {
    cursor: pointer;
  }
  button:disabled {
    cursor: not-allowed;
  }
</style>
