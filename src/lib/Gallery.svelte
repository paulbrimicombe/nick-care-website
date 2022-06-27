<script>
  /** @type {{ src: string, srcPreview: string, alt: string, width: number, height: number }[]} */
  export let images = [];

  /**
   * @type {HTMLDialogElement}
   */
  let dialog;

  /** @type {{ src: string, srcPreview: string, alt: string, width: number, height: number } | null} */
  let selectedImage = null;

  const onImageClick = (/** @type {HTMLElementEventMap['click']} */ event) => {
    /** @type {HTMLButtonElement | null}*/
    if (event?.target instanceof HTMLButtonElement) {
      const index = event.target.dataset.index;

      if (typeof index !== "undefined") {
        selectedImage = images[parseInt(index, 10)];
        dialog.showModal();
      }
    }
  };

  const nextImage = (/** @type {HTMLElementEventMap['click']} */ event) => {
    event?.preventDefault();
    const currentIndex = selectedImage ? images.indexOf(selectedImage) : -1;
    const newImage = images[currentIndex + 1];

    if (newImage) {
      selectedImage = newImage;
    }
  };

  const previousImage = (/** @type {HTMLElementEventMap['click']} */ event) => {
    event?.preventDefault();

    const currentIndex = selectedImage ? images.indexOf(selectedImage) : -1;
    const newImage = images[currentIndex - 1];

    if (newImage) {
      selectedImage = newImage;
    }
  };

  const onModalClose = (/** @type {HTMLElementEventMap['submit']} */ event) => {
    event?.preventDefault();
    selectedImage = null;
    dialog.close();
  };

  const handleKeydown = (
    /** @type {HTMLElementEventMap['keydown']} */ event
  ) => {
    if (selectedImage && event.key === "ArrowLeft") {
      previousImage();
    } else if (selectedImage && event.key === "ArrowRight") {
      nextImage();
    }
  };
</script>

<svelte:window on:keydown={handleKeydown} />

<dialog class="modal" bind:this={dialog}>
  <header>
    <form method="dialog" on:submit={onModalClose}>
      <ul>
        <li>
          <button
            class="gallery-nav previous"
            on:click={previousImage}
            disabled={!selectedImage || images.indexOf(selectedImage) === 0}
            >Previous</button
          >
        </li>
        <li>
          <button
            class="gallery-nav next"
            on:click={nextImage}
            disabled={!selectedImage ||
              images.indexOf(selectedImage) === images.length - 1}>Next</button
          >
        </li>
        <div class="spacer" />
        <li>
          <button value="default">Close</button>
        </li>
      </ul>
    </form>
  </header>
  <img
    id="modal-image"
    alt={selectedImage?.alt}
    src={selectedImage?.src}
    width={selectedImage?.width + "px"}
    height={selectedImage?.height + "px"}
  />
  <footer>
    <div>
      {selectedImage?.alt}
    </div>
  </footer>
</dialog>

<div>
  <div class="gallery">
    {#each images as image}
      <button on:click={onImageClick} data-index={images.indexOf(image)}>
        <img
          src={image.srcPreview}
          alt={image.alt}
          loading="lazy"
          width={image?.width + "px"}
          height={image?.height + "px"}
        />
      </button>
    {/each}
  </div>
</div>

<style>
  button {
    border: none;
  }

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
    max-height: 15em;
    object-fit: contain;
    width: auto;
    height: auto;
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
    box-shadow: 0 0 2em rgba(0, 0, 0, 1);
    position: relative;
  }

  .modal img {
    max-height: inherit;
    max-width: inherit;
    object-fit: contain;
    width: auto;
    height: auto;
  }

  .modal header {
    position: absolute;
    color: var(--heading-color);
    font-size: 0.8em;
    display: flex;
    width: 100%;
    flex-direction: row;
    justify-content: right;
    align-items: center;
  }

  .modal footer {
    position: absolute;
    bottom: 0;
    padding: 0.5em;
    background: #000000aa;
    width: 100%;
    color: #ddd;
  }

  .modal form {
    height: 3em;
    position: relative;
    background-color: #ffffffaa;
    width: 100%;
  }

  .modal form ul {
    padding: 0;
    margin: 0;
    height: 100%;
    display: flex;
    flex: 1;
    justify-content: start;
    align-items: center;
    list-style: none;
  }

  .modal form ul li {
    position: relative;
    height: 100%;
  }

  dialog[open] {
    animation: show 0.6s ease normal;
    margin-top: 5vh;
    z-index: 100;
    border-radius: 0.1em;
  }

  dialog::backdrop {
    animation: show 0.6s ease normal;
    background-color: rgba(0, 0, 0, 0.5);
    position: absolute;
    z-index: 1000;
    width: calc(100vw - (100vw - 100%));
    height: 100vh;
  }

  @keyframes show {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  .spacer {
    flex: 1;
  }

  .modal button {
    color: var(--heading-color);
    background-color: initial;
    height: 100%;
    font-weight: 700;
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    text-decoration: none;
    transition: color 0.2s linear;
    background-clip: 0.1rem;
    border: none;
    cursor: pointer;
  }

  .modal button[disabled] {
    color: #666;
  }

  .modal button[disabled]:hover {
    color: #666;
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

  .modal button[disabled]:hover::before {
    border-bottom: transparent;
  }

  .modal button:hover {
    color: var(--accent-color);
  }
</style>
