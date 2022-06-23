<script>
  // Param....
  /** @type {{ src: string, alt: string }[]} */
  export let images = [];

  /**
   * @type {HTMLDialogElement}
   */
  let dialog;

  /** @type {{ src: string, alt: string } | null} */
  let selectedImage = null;

  const onImageClick = (/** @type {HTMLElementEventMap['click']} */ event) => {
    /** @type {HTMLButtonElement | null}*/
    if (event?.target instanceof HTMLButtonElement) {
      const index = event.target.dataset.index;

      if (typeof index !== "undefined") {
        selectedImage = images[parseInt(index, 10)];
      }
    }
  };
</script>

<dialog
  class="modal"
  bind:this={dialog}
  on:close={() => {
    selectedImage = null;
    dialog.close();
  }}
  open={!!selectedImage}
>
  <header>
    <div>
      {selectedImage?.alt}
    </div>
    <form method="dialog">
      <button value="default">Close</button>
    </form>
  </header>
  <img id="modal-image" alt={selectedImage?.alt} src={selectedImage?.src} />
</dialog>

<div>
  <div class="gallery">
    {#each images as image}
      <button on:click={onImageClick} data-index={images.indexOf(image)}>
        <img src={image.src} alt={image.alt} loading="lazy" />
      </button>
    {/each}
  </div>
</div>

<style>
  .gallery {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    flex: auto;
    align-items: center;
    justify-content: center;
    gap: 1em;
  }

  .gallery button {
    border: none;
    background: inherit;
    padding: 0;
  }

  button img {
    pointer-events: none;
    max-height: 80vh;
    max-width: 100%;
  }

  button {
    cursor: pointer;
  }

  .modal {
    margin: auto;
    max-height: 90vh;
    max-width: 90vw;
    padding: 0;
    border: none;
    box-shadow: 0 0 2em  rgba(0, 0, 0, 1);
  }

  .modal img {
    max-height: inherit;
    max-width: inherit;
    object-fit: contain;
    padding-top: 3em;
  }

  .modal header {
    position: absolute;
    color: var(--heading-color);
    display: flex;
    width: 100%;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .modal header div {
    line-height: 2em;
    padding: 0.5em;
    color: var(--heading-color);
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .modal form {
    padding: 0.5em;
    position: relative;
  }

  dialog[open] {
    animation: show 0.6s ease normal;
    top: 5vh;
  }

  dialog[open]::backdrop {
    animation: show 0.6s ease normal;
    background-color: rgba(0, 0, 0, 0.5);
  }

  @keyframes show {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  .modal button {
    color: var(--heading-color);
    background-color: inherit;
    font-weight: 700;
    font-size: 0.8rem;
    height: 2em;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.2s linear;
    background-clip: 0.1rem;
    border: none;
    cursor: pointer;
  }

  .modal button::before {
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

  .modal button:hover::before {
    border-bottom: var(--size) solid var(--accent-color);
  }

  .modal button:hover {
    color: var(--accent-color);
  }
</style>
