<script type="module">
  /** @type string | null */
  export let variant = null;
</script>

<div class="container" class:full-width={variant === 'fullWidth'}>
  <slot />
</div>

<style>
  .container.full-width {
    max-width: unset;
  }

  .container {
    max-width: 1024px;
    display: flex;
    flex-direction: column;
    flex: 1;
    align-self: center;
    width: 100%;
    padding-left: 1em;
    padding-right: 1em;
    padding-bottom: 1em;
  }
</style>
