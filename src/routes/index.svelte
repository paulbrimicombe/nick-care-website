<script type="module">
  import { fade } from "svelte/transition";
</script>

<div in:fade={{ delay: 300, duration: 200 }} out:fade={{ duration: 200 }}>
  <h1>
    Nick Care celebration concert
    <div class="subtitle">Sunday 5th March 2023</div>
  </h1>
  <div class="container">
    <img src="nick.jpg" alt="Nick Care conducting junior brass" width="300px" />
    <div>
      <h2>About Nick</h2>
      <p>
        Nick Care was a much-loved trumpet player, educationalist, band
        director, teacher and friend. There will be a concert to celebrate his
        life on <b>Sunday 5th March 2023</b> in Buckinghamshire or Bedfordshire
        (location TBC). We would like as many people whose lives were touched by
        Nick to come together and celebrate Nick and all the amazing music he
        brought to our lives so please save the date now!
      </p>
      <p>
        Please see the <a href="/about">about Nick</a> page for more information
        about Nick and the various groups he conducted and played with.
      </p>
    </div>
  </div>

  <h2>About the concert</h2>

  <section>
    <h3>What groups will be playing?</h3>
    To give as many people as possible an opportunity to play, the concert will involve:
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
  </section>
  <section>
    <h3>Will there be rehearsals?</h3>
    <ul>
      <li>Sunday 5th March: Morning & Afternoon for all performers</li>
      <li>Saturday 4th March: Possibly some rehearsals for some performers</li>
    </ul>
  </section>
  <section>
    <h3>How can I get involved?</h3>
    <p>
      There are <em>plenty</em> of opportunities to get involved. If you'd like
      to play, please go to the <a href="/play">I'd like to play</a> page. If
      playing isn't your thing but you'd like to help with any of the following,
      please go to the
      <a href="/attend">I'd like to watch</a>
      page:
    </p>
    <ul>
      <li>Listen in the audience</li>
      <li>Help before the concert date</li>
      <li>Help on the concert day</li>
    </ul>
  </section>

  <style>
    .container {
      display: flex;
      gap: 1em;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      padding-bottom: 1em;
    }

    .container div {
      flex: 1;
      min-width: 300px;
      display: flex;
      flex-direction: column;
      gap: 1em;
    }

    .subtitle {
      font-size: 0.8em;
    }

    h1 {
      padding-bottom: 1rem;
    }

    section {
      padding-bottom: 1em;
    }
  </style>
</div>
