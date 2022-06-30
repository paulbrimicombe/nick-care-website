<script type="module">
import Footer from "./Footer.svelte";

  /** @type string | null */
  export let variant = null;
</script>

<div class="container" class:full-width={variant === 'fullWidth'}>
  <slot />
  <Footer/>
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
  }
</style>
