<script>
  import "../reset.css";
  import Header from "../lib/Header.svelte";
</script>

<Header />

<main>
  <slot />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    padding: 0;
    width: 100%;
    min-height: calc(100% - var(--header-height));
  }
</style>
