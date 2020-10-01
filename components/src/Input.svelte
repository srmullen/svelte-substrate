<script>

  const variants = {
    OUTLINE: 'outline',
    FILLED: 'filled',
    FLUSHED: 'flushed',
    UNSTYLED: 'unstyled'
  };

  const sizes = {
    SM: 'sm',
    MD: 'md',
    LG: 'lg'
  };

  /**
   * Properties of html input element
   */
  export let type = 'text';
  export let id;
  export let name;
  export let placeholder = '';
  export let value = '';
  export let disabled;

  // input reference
  let ref;

  /**
   * Component properties
   */
  export let variant = variants.OUTLINE;
  export let variantColor = 'gray';
  export let size = sizes.MD;

  $: if (ref) {
    ref.style.setProperty('--variant-color', `var(--${variantColor}-500)`);
    ref.style.setProperty('--variant-color-lighter', `var(--${variantColor}-200)`);
    ref.style.setProperty('--variant-color-darker', `var(--${variantColor}-700)`);
  }
</script>

<input 
  bind:this={ref}
  {id}
  {name}
  class="{size} {variant}"
  {placeholder}
  {type}
  {value}
  {disabled}
  on:blur
  on:click
  on:change
/>

<style>
  input {
    box-sizing: border-box;
    width: 100%;
    border: none;
    outline: none;
    transition: border-color 0.2s ease-in-out, box-shadow 0.2s ease-in-out, opacity 0.2s ease-in-out;
  }

  input:disabled {
    opacity: 0.5;
  }

  input:focus {
    border-color: var(--variant-color-darker);
    box-shadow: 0px 0px 0px 1px var(--variant-color-darker);
  }

  .sm {
    font-size: var(--typescale-helper);
    padding: var(--s1);
  }

  .md {
    font-size: var(--typescale-paragraph);
    padding: var(--s2);
  }

  .lg {
    font-size: var(--typescale-5);
    padding: var(--s3);
  }

  .outline {
    border: 1px solid var(--variant-color);
    border-radius: 4px;
  }

  /* .outline:focus {
    outline: solid var(--variant-color-lighter);
  } */

  .filled {
    background-color: var(--variant-color);
    border-radius: 4px;
    transition: background-color 0.2s ease-in-out;
  }

  .filled:focus {
    box-shadow: 0px 0px 0px 2px var(--variant-color-darker);
    background-color: transparent;
  }

  .flushed {
    border-bottom: 1px solid var(--variant-color);
  }

  .flushed:focus {
    border-bottom: 1px solid var(--variant-color-darker);
    box-shadow: 0px 1px 0px 0px var(--variant-color-darker);
  }

  .unstyled:focus {
    box-shadow: none;
    border: none;
  }
</style>