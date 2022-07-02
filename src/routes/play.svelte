<script>
  import PageTransition from "../lib/PageTransition.svelte";
  import Container from "../lib/Container.svelte";
  import Form from "../lib/Form.svelte";
</script>

<PageTransition>
  <Container>
    <h1>I'd like to play!</h1>
    <p>
      If you would like to attend but <em>not</em> play please go to
      <a href="/attend">this page</a> instead.
    </p>
    <Form
      src="https://docs.google.com/forms/d/1DCglsoj7J7vqeuWE3j06a_7RG3rB5V8PFKJD00dlSM0/viewform?embedded=true"
      title="Playing attendance form"
    />
  </Container>
</PageTransition>
