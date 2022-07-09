<script>
  import { page } from "$app/stores";
  import "../reset.css";
  import Header from "$lib/Header.svelte";
  const HOST = "https://www.nickcareconcert.co.uk";
</script>

<svelte:head>
  <meta name="description" content={$page.stuff.description} />
  <title>Nick Care Concert</title>

  <meta property="og:url" content={`${HOST}${$page.url.pathname}`} />
  <meta property="og:type" content="website" />
  <meta property="og:title" content={$page.stuff.title} />
  <meta property="og:description" content={$page.stuff.description} />
  <meta property="og:image" content={`${HOST}/logo.png`} />
  <meta property="og:image:width" content="1024" />
  <meta property="og:image:height" content="1024" />
  <meta property="og:og:locale" content="en_GB" />

  <meta name="twitter:card" content="summary" />
</svelte:head>

<Header />

<main>
  <slot />
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    padding: 0;
    width: 100%;
    min-height: calc(100% - var(--header-height));
  }
</style>
