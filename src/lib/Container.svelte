<div class="container">
  <slot />
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    flex: 1;
    align-self: center;
    width: 100%;
    max-width: 1024px;
    padding-left: 1em;
    padding-right: 1em;
  }
</style>
