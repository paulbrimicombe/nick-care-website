<script>
	import '../reset.css';
	import '../app.css';
	import Header from '../lib/Header.svelte'
</script>

<Header />

<main>
	<slot />
</main>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
	}
</style>
