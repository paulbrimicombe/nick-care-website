<script>
  import { page } from "$app/stores";
</script>

<header>
  <nav>
    <ul>
      <li class:active={$page.url.pathname === "/"}>
        <a sveltekit:prefetch href="/">Home</a>
      </li>
      <li class:active={$page.url.pathname === "/about/"}>
        <a sveltekit:prefetch href="/about">About Nick</a>
      </li>
      <li class:active={$page.url.pathname === "/attend/"}>
        <a sveltekit:prefetch href="/attend">I'd like to watch!</a>
      </li>
      <li class:active={$page.url.pathname === "/play/"}>
        <a sveltekit:prefetch href="/play">I'd like to play!</a>
      </li>
    </ul>
  </nav>
</header>

<style>
  header {
    display: flex;
    max-width: 1024px;
    width: 100%;
    margin: 0 auto;
    justify-content: space-between;
  }

  nav {
    display: flex;
		flex: 1;
    justify-content: center;
    --background: rgba(255, 255, 255, 0.7);
  }

  ul {
    position: relative;
    padding: 0;
    margin: 0;
    height: 3em;
    display: flex;
		flex: 1;
    justify-content: start;
    align-items: center;
    list-style: none;
    background: var(--background);
    background-size: contain;
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

  li.active::before, li:hover::before {
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

  a:hover {
    color: var(--accent-color);
  }
</style>
