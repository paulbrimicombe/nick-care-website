<script type="module">
  import { fade } from "svelte/transition";
</script>

<div in:fade={{ delay: 300, duration: 200 }} out:fade={{ duration: 200 }}>
  <h1>I'd like to watch!</h1>
  <p>
    If you would like to <em>perform</em> at the concert please go to <a href="/play"
      >this page</a
    > instead.
  </p>
  <iframe
    src="https://docs.google.com/forms/d/1NbJjjpUPtlsLNBEsWpzorfB_oiStQGRxgFbAutjC6rc/viewform?embedded=true"
    title="Attendance form"
  />
</div>

<style>
  div {
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  iframe {
    width: 100%;
    height: 100%;
    border: none;
  }
</style>
