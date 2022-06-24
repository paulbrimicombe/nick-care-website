<script>
  import PageTransition from "../lib/PageTransition.svelte";
  import Gallery from '../lib/Gallery.svelte'

  const images = [
    {
      src: "nick.jpg",
      alt: "Nick Care",
    },
    {
      src: "https://via.placeholder.com/180x200/100",
      alt: "180x200",
    },
    {
      src: "https://via.placeholder.com/140x250/100",
      alt: "140x250",
    },
    {
      src: "https://via.placeholder.com/1250x300/100",
      alt: "250x300",
    },
    {
      src: "https://via.placeholder.com/280x200/100",
      alt: "280x200",
    },
    {
      src: "https://via.placeholder.com/220x180/100",
      alt: "220x180",
    },
    {
      src: "https://via.placeholder.com/180x150/100",
      alt: "180x150",
    },
    {
      src: "https://via.placeholder.com/2210x2210/100",
      alt: "1210x1210",
    },
    {
      src: "https://via.placeholder.com/200x200/100",
      alt: "200x200",
    },
    {
      src: "https://via.placeholder.com/220x200/100",
      alt: "220x200",
    },
  ];
</script>

<PageTransition>
  <h1>Gallery</h1>
  <Gallery images={images}></Gallery>
</PageTransition>
