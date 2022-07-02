<footer>
  <span>
    <svg viewBox="0 0 512 512" width="20" fill="#00000099">
      <path
        d="M502.3 190.8c3.9-3.1 9.7-.2 9.7 4.7V400c0 26.5-21.5 48-48 48H48c-26.5 0-48-21.5-48-48V195.6c0-5 5.7-7.8 9.7-4.7 22.4 17.4 52.1 39.5 154.1 113.6 21.1 15.4 56.7 47.8 92.2 47.6 35.7.3 72-32.8 92.3-47.6 102-74.1 131.6-96.3 154-113.7zM256 320c23.2.4 56.6-29.2 73.4-41.4 132.7-96.3 142.8-104.7 173.4-128.7 5.8-4.5 9.2-11.5 9.2-18.9v-19c0-26.5-21.5-48-48-48H48C21.5 64 0 85.5 0 112v19c0 7.4 3.4 14.3 9.2 18.9 30.6 23.9 40.7 32.4 173.4 128.7 16.8 12.2 50.2 41.8 73.4 41.4z"
      />
    </svg>
    <a href="mailto:nickcareconcert@gmail.com"> nickcareconcert@gmail.com </a>
  </span>
  <span>&copy; {new Date().getFullYear()}</span>
</footer>

<style>
  svg {
    display: inline-block;
    max-height: 1.5em;
  }

  span {
    display: flex;
    gap: 0.5em;
  }

  @supports (-webkit-touch-callout: none) and (not (translate: none)) {
    span :not(:last-child) {
      margin-right: 0.5em;
    }
  }

  footer {
    flex: 0;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
    font-size: 0.8em;
    padding: 0.6em;
    gap: 1em;
    margin-top: 1em;
    border-bottom: 0;
    border-left: 0;
    border-right: 0;
    border-top: 5px solid;
    border-image-slice: 1;
    border-image-source: linear-gradient(
      to bottom right,
      var(--accent-color),
      var(--secondary-color-bright)
    );
  }
</style>
