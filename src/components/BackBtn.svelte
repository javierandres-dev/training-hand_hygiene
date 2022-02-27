<script>
  'use strict';
  export let reset, timer, minimum;
</script>

<button on:click={reset} disabled={timer > 0 && timer < minimum}>Back</button>

<style>
  button {
    width: 100%;
    border-color: coral;
    color: coral;
  }
  button:hover {
    cursor: pointer;
    opacity: 0.7;
  }
  button:disabled {
    cursor: not-allowed;
    opacity: 0.5;
    border-color: gray;
    color: gray;
  }
</style>
