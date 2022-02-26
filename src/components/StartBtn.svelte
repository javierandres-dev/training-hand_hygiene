<script>
  'use strict';
  export let start, timer;
</script>

<button on:click={start} disabled={timer !== 0}>Start</button>

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
