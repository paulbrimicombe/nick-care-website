<script>
  import PageTransition from "../lib/PageTransition.svelte";
  import Hero from "../lib/Hero.svelte";
  import HeroContent from "../lib/HeroContent.svelte";
</script>

<PageTransition>
  <Hero imageURL="/django-bates-tv-prog-2005-filtered.jpg">
    <HeroContent
      links={[
        {
          title: "Donate now!",
          url: "https://www.mndassociation.org/get-involved/donations/",
        },
      ]}
    >
      MND Association
      <img
        slot="logo"
        class="hero-logo"
        src="/mnd-logo.jpg"
        alt="Motor Neurone Disease Association logo"
        width="362px"
        height="150px"
      />
    </HeroContent>
  </Hero>
</PageTransition>

<style>
  .hero-logo {
    max-width: 20em;
    max-height: 8.28em;
    opacity: 0.9;
  }
</style>
