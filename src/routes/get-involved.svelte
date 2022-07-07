<script>
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
  import Hero from "../lib/Hero.svelte";
  import Form from "../lib/Form.svelte";
  import HeroContent from "$lib/HeroContent.svelte";
</script>

<PageTransition>
  <Hero imageURL="/btl-recording-filtered.jpg">
    <HeroContent links={[{ title: "Go to the form!", url: "#form" }]}>
      <span slot="title">Get Involved!</span>
      <span slot="subtitle">Let us know by filling <br/> in the form below</span>
      <img
        slot="logo"
        src="/logo.svg"
        alt="Logo"
        class="hero-logo"
        width="520px"
        height="520px"
      />
    </HeroContent>
  </Hero>
  <Container>
    <section class="forms">
      <span id="form" class="anchor" />
      <Form
        src="https://docs.google.com/forms/d/1mOBuKHVqvtVMlqeCHvd9tYYk_Pw5FWFMttgXGfiI1vI/viewform?embedded=true"
        title="Playing / help / attendance form"
      />
    </section>
  </Container>
</PageTransition>

<style>
  .hero-logo {
    max-width: 11em;
    max-height: 11em;
    opacity: 0.85;
  }

  section {
    margin-top: 0.5em;
  }

  .forms {
    display: flex;
    flex-direction: column;
    height: calc(90vh - var(--header-height));
  }

  .anchor {
    position: relative;
    top: calc(-1 * var(--header-height));
    visibility: hidden;
  }
</style>
