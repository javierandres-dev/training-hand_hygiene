<script>
  'use strict';
  import HowTo from './HowTo.svelte';

  export let reset;

  const title = 'Handrub',
    src = 'handrub.png',
    minimum = 20,
    better = 30;
</script>

<HowTo {title} {src} {minimum} {better} {reset} />
