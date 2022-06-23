<script type="module">
  import { fade } from 'svelte/transition'
</script>

<div in:fade={{ delay: 300, duration: 200 }} out:fade={{ duration: 200 }}>
  <h1>About</h1>

  <p>Some information about Nick perhaps?</p>
</div>
