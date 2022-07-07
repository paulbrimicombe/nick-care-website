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
    position: sticky;
    top: var(--header-height);
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
    align-items: center;
    padding: 1em 0;
    width: 100%;
  }

  .hero-title::before {
    content: "";
    height: 100%;
    border: none;
    border-left: 0.2em solid white;
    top: 0;
    left: 0;
    position: absolute;
    box-shadow: -1px -1px 3px #000c, 1px -1px 3px #000c, -1px 1px 3px #000c,
      1px 1px 3px #000c;  }

  .hero-title {
    position: relative;
    white-space: normal;
    padding: 0 0.5em;
    padding-left: 1.2em;
    margin: 0 0.5em;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    flex: 1;
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
    align-items: flex-end;
    justify-content: center;
  }

  .link-bar {
    padding: 0.5em 0;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
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
    transition: color, background-color 0.3s;
    position: relative;
    background-color: var(--white);
    background-color: var(--white-transparency);
    color: #333;
  }

  .link-bar a:hover {
    background-color: var(--white);
  }

  h1 {
    text-transform: capitalize;
    font-size: var(--step-4);
    color: #fff;
    text-shadow: -1px -1px 3px #000c, 1px -1px 3px #000c, -1px 1px 3px #000c,
      1px 1px 3px #000c;
    padding: 0;
  }

  .subtitle {
    font-size: var(--step-2);
    display: block;
  }
</style>
