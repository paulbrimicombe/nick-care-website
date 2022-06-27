<script type="module">
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
  import Gallery from "../lib/Gallery.svelte";
</script>

<PageTransition>
  <Container fullWidth={true}>
    <Gallery
      images={[
        {
          src: "/gallery/nick.jpg",
          alt: "Nick Care conducting",
        },
        {
          src: "/gallery/amc-db-doin-time.jpg",
          alt: "Doin' Time recording session",
        },
        {
          src: "/gallery/btl-recording.jpg",
          alt: "Beyond the Limit recording session with Salena Jones",
        },
        {
          src: "/gallery/tjb-rfh.jpg",
          alt: "Turnfurlong Jazz Band at the Royal Festival Hall",
        },
        {
          src: "/gallery/bernwode-festival-orch-2003.jpg",
          alt: "Bernwode Festival Orchestra 2003",
        },
        {
          src: "/gallery/jwb-winslow.jpg",
          alt: "Aylesbury Music Centre Junior Wind Band (Winslow)",
        },
        {
          src: "/gallery/brass-tacks.jpg",
          alt: "Brass Tacks",
        },
        {
          src: "/gallery/benslow-aug-10.jpg",
          alt: "Benslow",
        },
      ]}
    />
  </Container>
</PageTransition>
