<script>
  import { page } from "$app/stores";
</script>

<header>
  <nav>
    <ul>
      <li class:active={$page.url.pathname === "/"}>
        <a sveltekit:prefetch href="/"
          ><img
            src="/svg-logo.svg"
            alt="Logo"
            width="520px"
            height="520px"
          />Home</a
        >
      </li>
      <li class:active={$page.url.pathname === "/gallery/"}>
        <a sveltekit:prefetch href="/gallery">Gallery</a>
      </li>
      <li class:active={$page.url.pathname === "/attend/"}>
        <a sveltekit:prefetch href="/attend">Audience</a>
      </li>
      <li class:active={$page.url.pathname === "/play/"}>
        <a sveltekit:prefetch href="/play">I'd like to play</a>
      </li>
    </ul>
  </nav>
</header>

<style>
  header {
    position: sticky;
    top: 0;
    z-index: 1;
    background: #ffffffef;
    height: var(--header-height);
    padding-left: calc((100vw - 1024px) / 2);
    padding-right: calc((100vw - 1024px) / 2);
    background: linear-gradient(
      180deg,
      #ffffffee 0%,
      #ffffffcc 85%,
      #ffffff00 100%
    );
  }

  nav {
    height: calc(var(--header-height) - 0.5em);
  }

  ul {
    padding: 0;
    margin: 0;
    height: 100%;
    display: flex;
    flex: 1;
    justify-content: start;
    align-items: center;
    list-style: none;
  }

  li {
    position: relative;
    height: 100%;
  }

  li::before {
    --size: 5px;
    content: "";
    width: 90%;
    height: 0;
    position: absolute;
    bottom: var(--size);
    left: calc(5%);
    transition: border-color 0.2s linear;
    border-bottom: var(--size) solid transparent;
    pointer-events: none;
  }

  li.active::before,
  li:hover::before {
    border-bottom: var(--size) solid var(--accent-color);
  }

  nav a {
    display: flex;
    height: 100%;
    align-items: center;
    padding: 0 1em;
    color: var(--heading-color);
    font-weight: 700;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.2s linear;
    text-align: center;
    line-height: 1em;
  }

  nav a img {
    max-height: 2em;
    max-width: 2em;
    margin-right: 0.5em;
  }

  a:hover {
    color: var(--accent-color);
  }
</style>
