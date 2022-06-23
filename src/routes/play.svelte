<script type="module">
  import { fade } from "svelte/transition";
</script>

<div in:fade={{ delay: 300, duration: 200 }} out:fade={{ duration: 200 }}>
  <h1>I'd like to play!</h1>
  <p>If you would like to attend but <em>not</em> play please go to <a href="/attend">this page</a> instead.</p>
  <iframe
    src="https://docs.google.com/forms/d/1DCglsoj7J7vqeuWE3j06a_7RG3rB5V8PFKJD00dlSM0/viewform?embedded=true"
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
