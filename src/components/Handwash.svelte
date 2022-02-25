<script>
  import HowTo from './HowTo.svelte';

  const title = 'Handwash',
    duration = '40-60';
</script>

<h3>{title}</h3>
<HowTo src="handwash.png" alt={title} {duration} />
