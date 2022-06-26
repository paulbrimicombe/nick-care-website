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
    width: calc(100vw - calc(100vw - 100%));
    height: calc(100vh - calc(100vh - 100%) - var(--header-height) - 0.5em);
  }
</style>
