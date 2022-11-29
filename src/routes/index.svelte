<script context="module">
  /** @type {import('@sveltejs/kit').Load} */
  export async function load() {
    return {
      stuff: {
        title: "Nick Careʼs BIG Band Paean",
        description: "Nick Careʼs BIG Band Paean, Sunday 5th March 2023",
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
        //   url: "https://www.justgiving.com/team/NickCareConcert",
        // },
        { title: "Contact", url: "#contact" },
      ]}
    >
      <span slot="title">Nick Careʼs</span>
      <span slot="subtitle"
        >BIG Band Paean <br /> 6pm Sunday 5th March 2023</span
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
            Theatre, Exchange Street, Aylesbury, HP20 1UG, in aid of the Motor Neurone
            Disease Association (MNDA).
          </p>
          <p>
            <b>UPDATE:</b> Tickets are available NOW from the <a
              href="https://www.atgtickets.com/shows/nick-cares-big-band-paean/aylesbury-waterside-theatre/"
              target="_blank"
              referrerpolicy="no-referrer">Waterside Theatre event page</a
            >
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
          <h3>MNDA donations</h3>
          <p>
            Concert tickets are priced as low as we dared, to enable as many
            people to come as possible at £18 Adult &amp; £11.75
            Students/Children/ Registered unemployed. Rather more than I hoped
            to charge, but this includes the theatre’s various per ticket
            charges (but not the online transaction charge £2.25, which is not
            per ticket but per order).
          </p>
          <p>
            If you feel able &amp; have not done so yet, you might wish to
            donate something to the MNDA in memory of Nick via <a
              href="https://justgiving.com/team/NickCareConcert"
              target="blank"
              referrerpolicy="no-referrer"
              >Nick Care Concert fundraising for Motor Neurone Disease
              Association on JustGiving</a
            > or if you can’t attend, you might like to donate instead.
          </p>
          <p>
            We’ve asked the MNDA to earmark the majority of funds raised for
            research, with some also going to help the Bedfordshire Group of
            MNDA, who helped Nick so much with equipment and general support.
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
                A Brass/Wind Band playing two of Nickʼs Band compositions,
                directed by Kathy Gifford (strings etc. welcome as well?!)
              </li>
            </ul>
            Performers will be able to listen to the concert when not performing.
            It’s great that there are a lot of people who want to play. Although
            it will depend on how many people play specific instruments, it’s likely
            that most people will play in just one or two pieces plus the massed
            finale. This means that on the day there may be long gaps between your
            rehearsals &amp; the concert.
          </div>
          <div>
            <h3>Will there be rehearsals?</h3>
            <ul>
              <li>
                Saturday 4th March: Some rehearsals for some performers (at
                Aylesbury Music Centre, Walton Road, Aylesbury, HP21 7ST).
              </li>
              <li>
                Sunday 5th March: Morning &amp; Afternoon for all performers
                (from c. 11am TBC at the Theatre).
              </li>
            </ul>
            <p>
              Further information with the specific pieces that weʼll ask
              specific performers to play will be emailed in early 2023. A
              rehearsal schedule will be emailed to performers in the new year
              once itʼs been worked out! Performers will have seats reserved in
              the Upper Circle so they can listen when theyʼre not playing.
            </p>
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
                Audience? Buy your tickets! For Tickets bought at theatre box
                office, we think there is no additional transaction fee, or to
                buy tickets on line go to the <a
                  href="https://www.atgtickets.com/shows/nick-cares-big-band-paean/aylesbury-waterside-theatre/"
                  target="_blank"
                  referrerpolicy="no-referrer">Waterside Theatre event page</a
                >
              </li>
              <li>
                Please reply <em>as soon as possible,</em> and
                <b>definitely by 12/12/22</b>. Donʼt worry if youʼre unsure
                about your availability, weʼd like to know youʼre interested as
                soon as possible. DONʼT PUT IT OFF! 😊
              </li>
              <li>
                The form asks for a lot of info, but this means we get more of
                the info all in one go rather than in bits.
              </li>
              <li>
                If you miss the deadline, make contact anyway &amp; we’ll
                endeavour to include you if possible.
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
            If you have any questions or queries or anything that youʼd like to
            share with us not covered by the <a href="/get-involved"
              >Get Involved</a
            >
            form, please
            <a href="mailto:nickcareconcert@gmail.com"> email us </a>.
          </p>
          <p>
            After submitting the form on this website or sending us an email,
            you wonʼt hear anything for quite a while(!) as weʼll be processing
            the information sent by everyone to inform our future arrangements.
          </p>
          <h3>What on earth is a Paean???</h3>
          <ul>
            <li>
              A joyous song or hymn of praise, tribute, thanksgiving, or
              triumph;
            </li>
            <li>A work that praises or honours its subject;</li>
            <li>A tribute;</li>
            <li>A creative work expressing enthusiastic praise.</li>
          </ul>
          <em>&quot;a paean of praise for the great poets&quot;</em>
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

  ul :not(:last-child) {
    padding-bottom: 0.5em;
  }
</style>
