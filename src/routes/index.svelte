<script context="module">
  /** @type {import('@sveltejs/kit').Load} */
  export async function load() {
    return {
      stuff: {
        title: "Nick Care Concert",
        description: "Nick Care celebration concert, Sunday 5th March 2023",
      },
    };
  }
</script>

<script>
  import PageTransition from "$lib/PageTransition.svelte";
  import Container from "$lib/Container.svelte";
  import Hero from "$lib/Hero.svelte";
  import HeroContent from "$lib/HeroContent.svelte";
</script>

<PageTransition>
  <Hero imageURL="/amc-db-doin-time.jpg">
    <HeroContent
      links={[
        { title: "About", url: "#about" },
        { title: "Get Involved", url: "/get-involved" },
        // {
        //   title: "Donate",
        //   url: "https://www.mndassociation.org/get-involved/donations/",
        // },
        { title: "Contact", url: "#contact" },
      ]}
    >
      <span slot="title">Nick Care</span>
      <span slot="subtitle"
        >celebration concert <br /> 6pm Sunday 5th March 2023</span
      >
      <img
        slot="logo"
        src="/logo.svg"
        alt="Logo"
        class="hero-logo"
        width="520px"
        height="520px"
      />
    </HeroContent>
  </Hero>
  <Container>
    <section>
      <h2 class="heading">About Nick<span id="about" class="anchor" /></h2>
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
            director, teacher and friend. There will be a charity concert to
            celebrate his life at <b>6pm on Sunday 5th March 2023</b> at the Waterside
            Theatre, Aylesbury or at a Bedfordshire venue (location TBC) in aid of
            the Motor Neurone Disease Association (MNDA).
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
      <h2 class="heading">About the concert</h2>
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
            Anyone who played in a band that Nick directed is invited to play in
            this concert. Performers will be grouped into:

            <ul>
              <li>
                Big Bands directed by <a
                  href="https://www.julesbuckley.com/"
                  target="_blank"
                  referrerpolicy="no-referrer">Jules Buckley</a
                > (Metropole Orkest, BBC Symphony Orchestra, BBC Proms conductor…
                and AMC Dance Band member)
              </li>
              <li>
                A Brass/Wind Band playing two of Nick's Band compositions,
                directed by Kathy Gifford (strings etc. welcome as well?!)
              </li>
            </ul>
            Performers will be able to listen to the concert when not performing.
            We hope that a lot of people will want to play. In this case, it's likely
            that most people will play in just one or two pieces plus the massed
            finale. This means that on the day there may be long gaps between your
            rehearsals & the concert.
          </div>
          <div>
            <h3>Will there be rehearsals?</h3>
            <ul>
              <li>
                Sunday 5th March: Morning & Afternoon for all performers (from
                11am TBC)
              </li>
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
              There are <em>plenty</em> of opportunities to get involved:
            </p>
            <ul>
              <li>
                Like to Play and/or help? Go to the <a href="/get-involved"
                  >"Get Involved"</a
                > page & complete & submit the form.
              </li>
              <li>
                Audience? You'll need to get tickets once they're released by
                the theatre. BUT if you complete & submit the form on the <a
                  href="/get-involved">"Get Involved"</a
                > page you'll halp us gauge the likely size of the audience!
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section>
      <h2 class="heading">Contact<span id="contact" class="anchor" /></h2>
      <div class="image-and-text">
        <span
          class="img"
          role="img"
          style="background-image: url(/with-trumpet.jpg); background-position: center top"
          aria-label="Nick Care sitting on a bench with his trumpet"
        />
        <div class="text">
          <p>
            If you have any questions or queries or anything that you'd like to
            share with us not covered by the <a href="/get-involved"
              >Get Involved</a
            >
            form, please
            <a href="mailto:nickcareconcert@gmail.com"> email us </a>.
          </p>
        </div>
      </div>
    </section>
  </Container>
</PageTransition>

<style>
  .hero-logo {
    max-width: 11em;
    max-height: 11em;
    opacity: 0.85;
  }

  ul {
    margin-top: 0.5em;
    margin-bottom: 0.5em;
  }

  section {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    gap: 1em;
    margin-top: 0.5em;
  }

  .anchor {
    position: relative;
    top: calc(-1 * var(--header-height));
    visibility: hidden;
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
