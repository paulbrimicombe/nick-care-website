<script type="module">
  import PageTransition from "../lib/PageTransition.svelte";
  import Form from "../lib/Form.svelte";
</script>

<PageTransition>
  <h1>I'd like to watch!</h1>
  <p>
    If you would like to <em>perform</em> at the concert please go to
    <a href="/play">this page</a> instead.
  </p>
  <Form src="https://docs.google.com/forms/d/1NbJjjpUPtlsLNBEsWpzorfB_oiStQGRxgFbAutjC6rc/viewform?embedded=true" title="Attendance form" />
</PageTransition>

<style>
  div {
    flex: 1;
    display: flex;
    flex-direction: column;
  }
</style>
