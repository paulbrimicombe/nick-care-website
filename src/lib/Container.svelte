<script type="module">
  export let fullWidth = false;
</script>

<div class="container" class:narrow={!fullWidth}>
  <slot />
</div>

<style>
  .narrow {
    max-width: 1024px;
  }

  .container {
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
