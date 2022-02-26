<script>
  'use strict';
  import HowTo from './HowTo.svelte';

  export let reset;

  const title = 'Handwash',
    src = 'handwash.png',
    minimum = 40,
    better = 60;
</script>

<HowTo {title} {src} {minimum} {better} {reset} />
