<script context="module">
  /** @type {import('@sveltejs/kit').Load} */
  export async function load() {
    return {
      stuff: {
        title: "Nick Careʼs BIG Band Paean: Get Involved",
        description: "How to get involved in Nick Careʼs BIG Band Paean",
      },
    };
  }
</script>

<script>
  import PageTransition from "$lib/PageTransition.svelte";
  import Container from "$lib/Container.svelte";
  import Form from "$lib/Form.svelte";
</script>

<PageTransition>
  <Container>
    <section class="forms">
      <Form
        src="https://docs.google.com/forms/d/1mOBuKHVqvtVMlqeCHvd9tYYk_Pw5FWFMttgXGfiI1vI/viewform?embedded=true"
        title="Playing / help / attendance form"
      />
    </section>
  </Container>
</PageTransition>

<style>
  .forms {
    display: flex;
    flex-direction: column;
    height: calc(92vh - var(--header-height));
  }
</style>
