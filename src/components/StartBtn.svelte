<script>
  'use strict';
  export let start, timer;
</script>

<button on:click={start} disabled={timer !== 0}>Start</button>

<style>
  button {
    width: 100%;
    border-color: skyblue;
    color: skyblue;
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
