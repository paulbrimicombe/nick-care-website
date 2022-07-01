<script>
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
</script>

<PageTransition>
  <div class="hero">
    <div class="container">
      <h1>
        <img src="/logo.svg" alt="Logo" width="520px" height="520px" />
        <div>
          Nick Care celebration concert
          <div class="subtitle">Sunday 5th March 2023</div>
        </div>
      </h1>
    </div>
  </div>
  <Container>
    <section>
      <h2>About Nick</h2>
      <div class="image-and-text">
        <span
          class="img"
          role="img"
          style="background-image: url(/nick.jpg); min-height: 25em;"
          aria-label="Nick Care conducting"
        />
        <div class="text">
          <p>
            Nick Care was a much-loved trumpet player, educationalist, band
            director, teacher and friend. There will be a concert to celebrate
            his life on <b>Sunday 5th March 2023</b> in Buckinghamshire or Bedfordshire
            (location TBC).
          </p>
          <p>
            We would like as many people whose lives were touched by Nick to
            come together and celebrate Nick and all the amazing music he
            brought to our lives so please save the date now and <strong
              >share this site far and wide</strong
            >!
          </p>
          <p>
            Please see the <a href="/gallery">gallery</a> page for some pictures
            of Nick and the various groups he conducted and played with.
          </p>
        </div>
      </div>
    </section>

    <section>
      <h2>About the concert</h2>
      <div class="image-and-text">
        <span
          class="img"
          role="img"
          style="background-image: url(/btl-recording.jpg)"
          aria-label="Nick Care conducting AMC Dance Band with Selena Jones (Beyond the Limit recording session, 1999)"
        />
        <div class="text">
          <div>
            <h3>Who will play at the concert?</h3>
            If you played in a band under Nick's direction, then you are invited
            to play. Performers will be grouped into:

            <ul>
              <li>
                Big Bands directed by <a
                  href="https://www.julesbuckley.com/"
                  target="_blank"
                  referrerpolicy="no-referrer">Jules Buckley</a
                > (Metropole Orkest, BBC Symphony Orchestra, BBC Proms conductor…)
              </li>
              <li>
                A Brass/Wind Band directed by Kathy Gifford (strings etc.
                welcome as well?!)
              </li>
            </ul>
            Depending on numbers, most people will play in just one or two pieces
            plus the massed finale. This means that on the day there might be long
            gaps between your rehearsal & the concert.
          </div>
          <div>
            <h3>Will there be rehearsals?</h3>
            <ul>
              <li>Sunday 5th March: Morning & Afternoon for all performers</li>
              <li>
                Saturday 4th March: Possibly some rehearsals for some performers
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="image-and-text">
        <span
          class="img"
          role="img"
          style="background-image: url(/tjb-rfh.jpg)"
          aria-label="Turnfurlong Jazz Band at the Royal Festival Hall (c. 2003)"
        />
        <div class="text">
          <div>
            <h3>How can I get involved?</h3>
            <p>
              There are <em>plenty</em> of opportunities to get involved. If
              you'd like to play, please go to the
              <a href="/play">performing</a>
              page. If playing isn't your thing but you'd like to help with any of
              the following, please go to the
              <a href="/attend">audience</a>
              page:
            </p>
            <ul>
              <li>Listen in the audience</li>
              <li>Help before the concert date</li>
              <li>Help on the concert day</li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </Container>
</PageTransition>

<style>
  .hero {
    margin: 0;
    position: relative;
    height: calc(90vh - var(--header-height));
    display: flex;
    flex-direction: column;
  }

  .hero::before {
    content: "";
    width: calc(100vw - (100vw - 100%));
    height: 90vh;
    position: absolute;
    margin-top: calc(-1 * var(--header-height));
    background-image: url(/amc-db-doin-time.jpg);
    background-position: center top;
    background-repeat: no-repeat;
    background-size: cover;
    filter: blur(0.5px);
  }

  .hero > .container {
    max-width: 1024px;
    margin: 0 auto;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }

  .subtitle {
    font-size: 0.8em;
  }

  h1 {
    --padding: 0.5em;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 0.5em;
    text-transform: capitalize;
    text-align: center;
    padding: var(--padding);
    margin: 0.5em;
    align-items: center;
    background: #ffffffcc;
    border: 10px solid;
    border-image-slice: 1;
    border-width: 5px;
    border-image-source: linear-gradient(
      to bottom right,
      var(--accent-color),
      var(--secondary-color-bright)
    );
    position: sticky;
    top: calc(var(--header-height) + var(--padding));
  }

  ul {
    margin-top: 0.5em;
    margin-bottom: 0.5em;
  }

  h1 img {
    max-width: 4em;
    max-height: 4em;
  }

  section {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    gap: 1em;
  }

  h2 {
    padding-top: 0.5em;
    position: relative;
  }

  h2::after {
    content: "";
    border-top: 0;
    border-left: 0;
    border-right: 0;
    border-bottom: 5px solid;
    border-image-slice: 1;
    border-image-source: linear-gradient(
      to top right,
      var(--accent-color),
      var(--secondary-color-bright)
    );
    position: absolute;
    height: 1.5em;
    left: 0;
    width: 100%;
  }

  .image-and-text {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 1em;
    align-items: center;
    justify-content: center;
  }

  @supports (-webkit-touch-callout: none) and (not (translate: none)) {
    .image-and-text > :not(:last-child) {
      margin-right: 1em;
    }

    .image-and-text > .text > :not(:last-child) {
      margin-bottom: 1em;
    }

    section > :not(:last-child) {
      margin-bottom: 1em;
    }
  }

  .image-and-text > .img {
    flex: 1;
    min-height: 20em;
    min-width: 15em;
    width: 100%;
    align-self: stretch;
    background-position: center center;
    background-size: cover;
    opacity: 1;
  }

  .image-and-text > .text {
    flex: 1;
    min-width: 20em;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 1em;
  }
</style>
