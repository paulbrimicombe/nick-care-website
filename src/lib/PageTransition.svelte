<script type="module">
  import { fade } from "svelte/transition";

  let state = "";

  const inDelay = 300;
  const duration = 200;

  const onIntroStart = () => {
    state = "INTRO_START";
    setTimeout(() => {
      state = "VISIBLE";
      setTimeout(() => {
        state = "FADING_IN";
      });
    }, inDelay);
  };
</script>

<div
  in:fade={{ duration: 0 }}
  out:fade={{ duration }}
  on:introstart={onIntroStart}
  class={state === "INTRO_START"
    ? "intro-start"
    : state === "VISIBLE"
    ? "visible"
    : state === "FADING_IN"
    ? "fading-in"
    : ""}
>
  {#if state !== "INTRO_START"}
    <slot />
  {/if}
</div>

<style>
  div {
    display: flex;
    flex-direction: column;
    flex: 1;
    transition: opacity 0.2s;
  }

  .intro-start {
    display: none;
    opacity: 0;
  }

  .visible {
    opacity: 0;
  }

  .fading-in {
    opacity: 1;
  }
</style>
