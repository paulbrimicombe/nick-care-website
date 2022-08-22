<script>
  export /**
   * @type {{ title: string, url: string }[]}
   */
  let links = [];
</script>

<div class="hero-content">
  <div class="hero-logo" class:has-logo={$$slots.logo}>
    <slot name="logo" />
  </div>
  <div class="hero-title">
    <h1>
      <slot name="title" />
      <span class="subtitle">
        <slot name="subtitle" />
      </span>
    </h1>
    <div class="link-bar">
      {#each links as link}
        <a
          href={link.url}
          target={link.url?.startsWith("http") ? "blank" : ""}
          referrerpolicy={link.url?.startsWith("http") ? "no-referrer" : ""}
          >{link.title}</a
        >
      {/each}
    </div>
  </div>
</div>

<style>
  .hero-content {
    --padding: 0.5em;
    position: sticky;
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
    align-items: center;
    padding: 1em 0;
    text-transform: capitalize;
    text-align: center;
    margin: var(--padding);
    background: #ffffffcc;
    border: 0.5em solid;
    border-image-slice: 1;
    border-width: 0.5em;
    border-image-source: linear-gradient(
      to bottom right,
      var(--accent-color),
      var(--secondary-color-bright)
    );
    top: calc(var(--header-height) + var(--padding));
  }

  .hero-title {
    position: relative;
    white-space: normal;
    padding: 0 0.5em;
    margin: 0 0.5em;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-width: 15em;
    min-height: 10em;
  }

  .hero-logo.has-logo {
    display: flex;
  }

  .hero-logo {
    flex: 0.5;
    display: none;
    padding: 0 1em;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .link-bar {
    padding: 0.5em 0;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
  }

  .link-bar a {
    text-transform: uppercase;
    font-weight: 700;
    font-size: var(--step--1);
    border: 3px solid #fff;
    cursor: pointer;
    overflow: hidden;
    padding: 0.5em 0.8em;
    margin: 0.2em;
    text-align: center;
    text-decoration: none;
    transition: color, background-color, border-color 0.3s;
    position: relative;
    background-color: var(--white);
    background-color: transparent;
    color: #333;
  }

  .link-bar a:hover {
    background-color: #d0d0d0;
    border-color: var(--heading-color);
  }

  h1 {
    text-transform: capitalize;
    font-size: var(--step-4);
    color: var(--heading-color);
    padding: 0;
  }

  .subtitle {
    font-size: var(--step-2);
    display: block;
  }
</style>
