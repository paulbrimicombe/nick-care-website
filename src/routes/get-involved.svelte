<script>
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
  import Hero from "../lib/Hero.svelte";
  import Form from "../lib/Form.svelte";
  import HeroContent from "$lib/HeroContent.svelte";
</script>

<PageTransition>
  <Hero imageURL="/btl-recording-filtered.jpg">
    <HeroContent links={[{ title: "Fill in the form!", url: "#play" }]}>
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
      <span id="play" class="anchor" />
      <Form
        src="https://docs.google.com/forms/d/1DCglsoj7J7vqeuWE3j06a_7RG3rB5V8PFKJD00dlSM0/viewform?embedded=true"
        title="Playing attendance form"
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
