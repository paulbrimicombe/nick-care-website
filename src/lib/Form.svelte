<script>
  import { fade } from "svelte/transition";

  export let src = "";
  export let title = "";

  let loaded = false;

  const handleIFrameLoad = () => {
    loaded = true;
  };
</script>

<div class="iframe-container">
  {#if !loaded}
    <div class="spinner" out:fade={{ delay: 200, duration: 300 }}>
      <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <circle cx="50" cy="50" r="45" />
      </svg>
    </div>
  {/if}
  <iframe
    class={loaded ? "" : "hidden"}
    {src}
    {title}
    on:load={handleIFrameLoad}
  />
</div>

<style>
  div {
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  iframe {
    width: 100%;
    flex: 1;
    border: none;
    transition: opacity 1s 0.3s;
  }

  .iframe-container {
    position: relative;
  }

  .spinner {
    height: 100%;
    width: 100%;
    position: absolute;
    display: flex;
    align-items: center;
    justify-items: center;
    z-index: 1;
  }

  .spinner::before {
    content: "";
    position: absolute;
    top: 5px;
    border-radius: 2px;
    width: calc(100% - 2px);
    height: calc(100% - 2px);
    background-color: #11111122;
    box-shadow: #11111122 0px 0px 2px 2px;
  }

  .hidden {
    opacity: 0;
  }

  svg {
    animation: 2s linear infinite svg-animation;
    max-width: 3em;
    flex: 1;
  }

  @keyframes svg-animation {
    0% {
      transform: rotateZ(0deg);
    }
    100% {
      transform: rotateZ(360deg);
    }
  }

  circle {
    animation: 1.4s ease-in-out infinite both circle-animation;
    display: block;
    fill: transparent;
    stroke: var(--accent-color);
    stroke-linecap: round;
    stroke-dasharray: 283;
    stroke-dashoffset: 280;
    stroke-width: 10px;
    transform-origin: 50% 50%;
  }

  @keyframes circle-animation {
    0%,
    25% {
      stroke-dashoffset: 280;
      transform: rotate(0);
    }

    50%,
    75% {
      stroke-dashoffset: 75;
      transform: rotate(45deg);
    }

    100% {
      stroke-dashoffset: 280;
      transform: rotate(360deg);
    }
  }
</style>
