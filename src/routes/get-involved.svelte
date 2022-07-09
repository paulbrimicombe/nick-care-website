<script context="module">
  /** @type {import('@sveltejs/kit').Load} */
  export async function load() {
    return {
      stuff: {
        title: "Nick Care Concert: Get Involved",
        description: "How to get involved in the Nick Care celebration concert",
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
  section {
    margin-top: 0.5em;
  }

  .forms {
    display: flex;
    flex-direction: column;
    height: calc(90vh - var(--header-height));
  }
</style>
