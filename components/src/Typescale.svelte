<script>
  import { onMount } from 'svelte';

  const scales = {
    MINOR_SECOND: 1.067,
    MAJOR_SECOND: 1.125,
    MINOR_THRID: 1.2,
    MAJOR_THRID: 1.25,
    PERFECT_FOURTH: 1.333,
    AUGMENTED_FOURTH: 1.414,
    PERFECT_FIFTH: 1.5,
    GOLDEN_RATIO: 1.618
  };

  export let scale = scales.MAJOR_SECOND;

  onMount(() => {
    setTypescale();
  });

  function setTypescale() {
    const paragraph = 1;
    const h6 = 1;
    const h5 = scale;
    const h4 = h5 * scale;
    const h3 = h4 * scale;
    const h2 = h3 * scale;
    const h1 = h2 * scale;
    const helper = paragraph / scale;
    const copyright = helper / scale;
    document.documentElement.style.setProperty(`--typescale-1`, `${h1.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-2`, `${h2.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-3`, `${h3.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-4`, `${h4.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-5`, `${h5.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-6`, `${h6.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-paragraph`, `${paragraph.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-helper`, `${helper.toFixed(2)}rem`);
    document.documentElement.style.setProperty(`--typescale-copyright`, `${copyright.toFixed(2)}rem`);
  }
</script>