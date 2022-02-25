<script>
  export let src, alt, duration;
  const origin = 'World Health Organization',
    path = 'https://www.who.int/campaigns/world-hand-hygiene-day';
</script>

<p>Duration of the entire procedure: {duration} seconds.</p>
<figure>
  <img {src} {alt} />
  <figcaption>
    Taken from <a href={path} target="_blank" rel="noopener noreferrer"
      >{origin}</a
    >
  </figcaption>
</figure>
