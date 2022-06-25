<script type="module">
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
</script>

<PageTransition>
  <Container>
    <h1>About</h1>

    <p>Some information about Nick perhaps?</p>
  </Container>
</PageTransition>

<style>
  p {
    flex: 1;
  }
</style>
