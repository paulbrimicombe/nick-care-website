<script>
  import "../reset.css";
  import "../app.css";
  import Header from "../lib/Header.svelte";
</script>

<Header />

<main>
  <slot />
</main>

<style>
  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 0;
    width: 100%;
    height: calc(100% - var(--header-height));
  }
</style>
