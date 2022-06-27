<script type="module">
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
</script>

<PageTransition>
  <div class="hero">
    <div class="container">
      <h1>
        Nick Care celebration concert
        <div class="subtitle">Sunday 5th March 2023</div>
      </h1>
    </div>
  </div>
  <Container>
    <section>
      <h2>About Nick</h2>
      <div class="image-and-text">
        <img
          src="/nick.jpg"
          alt="Nick Care conducting"
          width="352px"
          height="429px"
          loading="lazy"
        />
        <div class="text">
          <p>
            Nick Care was a much-loved trumpet player, educationalist, band
            director, teacher and friend. There will be a concert to celebrate
            his life on <b>Sunday 5th March 2023</b> in Buckinghamshire or Bedfordshire
            (location TBC). We would like as many people whose lives were touched
            by Nick to come together and celebrate Nick and all the amazing music
            he brought to our lives so please save the date now!
          </p>
          <p>
            Please see the <a href="/about">about Nick</a> page for more information
            about Nick and the various groups he conducted and played with.
          </p>
        </div>
      </div>
    </section>

    <section>
      <h2>About the concert</h2>
      <div class="image-and-text">
        <img
          src="/btl-recording.jpg"
          width="352px"
          height="238px"
          alt="Nick Care conducting AMC Dance Band with Selena Jones (Beyond the Limit recording session, 1999)"
          loading="lazy"
        />
        <div class="text">
          <div>
            <h3>What groups will be playing?</h3>
            To give as many people as possible an opportunity to play, the concert
            will involve:
            <ul>
              <li>
                Big Band(s) directed by <a
                  href="https://www.julesbuckley.com/"
                  target="_blank"
                  referrerpolicy="no-referrer">Jules Buckley</a
                > (Metropole Orkest, BBC Symphony Orchestra…)
              </li>
              <li>Brass / Wind Band directed by Kathy Gifford</li>
            </ul>
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
        <img
          src="/tjb-rfh.jpg"
          width="352px"
          height="237px"
          alt="Turnfurlong Jazz Band at the Royal Festival Hall (c. 2003)"
          loading="lazy"
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
    z-index: -1;
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
    color: var(--heading-color);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    text-transform: capitalize;
    text-align: center;
    padding: var(--padding);
    margin: 0.5em;
    align-items: center;
    border-radius: 0.5em;
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
    border-bottom: var(--accent-color) solid 3px;
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

  .image-and-text > img {
    width: 25%;
    min-width: 20em;
    flex: 0;
    display: flex;
    flex-direction: column;
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
