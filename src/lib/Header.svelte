<script>
  import { page } from "$app/stores";
</script>

<header>
  <nav>
    <ul>
      <li class:active={$page.url.pathname === "/"}>
        <a sveltekit:prefetch href="/"
          ><img
            src="/logo-small.svg"
            alt="Logo"
            width="520px"
            height="520px"
          />Home</a
        >
      </li>
      <li class:active={$page.url.pathname === "/get-involved/"}>
        <a sveltekit:prefetch href="/get-involved">Get involved</a>
      </li>
      <li class:active={$page.url.pathname === "/gallery/"}>
        <a sveltekit:prefetch href="/gallery">Gallery</a>
      </li>
      <!-- <li class:active={$page.url.pathname === "/donate/"}>
        <a sveltekit:prefetch href="/donate">Donate</a>
      </li> -->
    </ul>
  </nav>
</header>

<style>
  header {
    position: sticky;
    top: 0;
    z-index: 1;
    background: #e1e4e9ee;
    height: var(--header-height);
    padding-left: calc((100vw - 1024px) / 2);
    padding-right: calc((100vw - 1024px) / 2);
    background: linear-gradient(
      180deg,
      #e1e4e9ee 0%,
      #e1e4e9cc 85%,
      #e1e4e900 100%
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
    --size: 0.25em;
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
    font-size: var(--step--2);
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
