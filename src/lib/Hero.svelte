<script>
  export let imageURL = "";

  export let variant = "";
</script>

<div
  class="hero"
  class:midi={variant === "midi"}
  style={`--image-url: url(${imageURL})`}
>
  <div class="spacer" />
  <slot />
</div>

<style>
  .spacer {
    flex: 0.3;
  }

  .hero.midi {
    --hero-height: 80vh;
  }

  .hero {
    --hero-height: 100vh;
    margin: 0;
    position: relative;
    height: calc(var(--hero-height) - var(--header-height));
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .hero::before {
    content: "";
    width: calc(100vw - (100vw - 100%));
    height: var(--hero-height);
    position: absolute;
    margin-top: calc(-1 * var(--header-height));
    background-image: var(--image-url);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    z-index: -1;
  }
</style>
