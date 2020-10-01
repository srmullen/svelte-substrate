<script>
  const variants = {
    SOLID: 'solid',
    GHOST: 'ghost',
    OUTLINE: 'outline',
    LINK: 'link',
    UNSTYLED: 'unstyled'
  };

  const sizes = {
    XS: 'xs',
    SM: 'sm',
    MD: 'md',
    LG: 'lg',
    XL: 'xl'
  }

  export let size = sizes.MD;
  export let variant = variants.SOLID;
  export let variantColor = 'gray';
  export let disabled;

  let ref;

  // Set variant color
  $: if (ref) {
    ref.style.setProperty('--variant-color', `var(--${variantColor}-600)`);
    ref.style.setProperty('--variant-color-lighter', `var(--${variantColor}-200)`);
    ref.style.setProperty('--variant-color-darker', `var(--${variantColor}-700)`);
  }

</script>

<button 
  class="substrate {variant} {size}"
  bind:this={ref}
  {disabled}
  on:click
  on:hover
  on:focus
>
  <slot />
</button>

<style>
  button {
    --color: var(--gray-500);
  }

  button {
    border-radius: 6px;
    border: none;
    cursor: pointer;
    user-select: none;
    appearance: none;
    white-space: nowrap;
    font-weight: 600;
  }

  button:disabled {
    opacity: 0.5;
  }

  .solid {
    color: white;
    background-color: var(--variant-color);
    transition: background-color 0.2s ease-in-out;
  }

  .solid:hover:enabled {
    background-color: var(--variant-color-darker);
  }

  .ghost {
    color: var(--variant-color);
    background-color: transparent;
    transition: background-color 0.2s ease-in-out;
  }

  .ghost:hover:enabled {
    background-color: var(--variant-color-lighter);
  }

  .outline {
    background-color: transparent;
    border: 1px solid var(--variant-color);
    color: var(--variant-color);
    transition: background-color 0.2s ease-in-out;
  }

  .outline:hover:enabled {
    background-color: var(--variant-color-lighter);
    transition: background-color 0.2s ease-in-out;
  }

  .link {
    color: var(--variant-color);
    padding: 0;
    background: none;
  }

  .link.xs,
  .link.sm,
  .link.md,
  .link.lg,
  .link.xl {
    padding: 0;
    margin: var(--s4);
  }

  .link:hover:enabled {
    text-decoration: underline;
  }

  .xs {
    font-size: var(--typescale-helper);
    padding: var(--s1) var(--s2);
  }

  .sm {
    font-size: var(--typescale-helper);
    padding: var(--s2) var(--s4);
  }

  .md {
    font-size: var(--typescale-paragraph);
    padding: var(--s3) var(--s6);
  }

  .lg {
    font-size: var(--typescale-paragraph);
    padding: var(--s4) var(--s8);
  }

  .xl {
    font-size: var(--typescale-5);
    padding: var(--s6) var(--s10);
  }
</style>